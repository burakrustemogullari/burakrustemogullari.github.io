# 4 · OFDM ve CSI

!!! info "Durum: taslak"

**Ön koşul:** [3 · Çok yollu kanal](cok-yollu-kanal.md)

**Bu modülün sonunda:**

- OFDM'in bandı alt taşıyıcılara nasıl böldüğünü ve IFFT/FFT ile nasıl çalıştığını anlatabilirsin.
- CSI'nin bir paketin eğitim alanından $\hat H_k = Y_k / X_k$ ile nasıl kestirildiğini gösterebilirsin.
- CSI tensörünün eksenlerini (alıcı anten × verici anten × alt taşıyıcı × zaman)
  ve her eksenin neyi kodladığını açıklayabilirsin.
- CSI'nin RSSI'dan neden daha zengin olduğunu sayılarla anlatabilirsin.

## Konular

- Modülasyon: bit → sembol, QPSK ve QAM takımyıldızları
- OFDM: alt taşıyıcı aralığı $\Delta f$, FFT boyutu, veri/pilot/DC/koruma kutuları
- Verici IFFT, alıcı FFT; dikgenlik koşulu $\Delta f = 1/T_{sym}$
- Döngüsel önek ve semboller arası girişim
- Paketin önsözü: STF, LTF, SIG; kanal kestirimi LTF'den yapılır
- MIMO: birden çok akışın LTF'ler ile ayrılması
- Standartlara göre boyutlar: 802.11n/ac'de 312,5 kHz aralık, 802.11ax'te 78,125 kHz;
  20/40/80/160 MHz'de kullanılan alt taşıyıcı sayıları
- I/Q: çipin verdiği iki tamsayıdan genlik ve faz hesaplamak
- CSI tensörü ve dilimleri: CFR (frekans), MIMO matrisi (uzay), zaman serisi
- RSSI ile karşılaştırma

## Kaynaklar

- Özel kaynak: Wi-Fi Algılama Laboratuvarı, T3 bölümü
- Hands-on Wireless Sensing eğitimi, CSI ve OFDM bölümleri:
  <https://tns.thss.tsinghua.edu.cn/wst/docs/intro/>

## Kod alıştırmaları

1. **Mini OFDM:** 64 alt taşıyıcılı bir OFDM sembolünü IFFT ile üret, döngüsel
   önek ekle, modül 3'teki kanal simülatöründen geçir, gürültü ekle.
2. Alıcıda FFT uygula, bilinen ±1 desenli bir LTF ile $\hat H_k$'yı kestir ve
   gerçek CFR ile karşılaştır. SNR düşünce kestirimin nasıl bozulduğunu göster.
3. 2 verici ve 2 alıcı antenli bir kanalda iki LTF ile dört kanalı ayır.
4. Paketleri zamanla tekrarla ve `(Nrx, Ntx, Nsc, T)` şeklinde sentetik bir CSI tensörü oluştur.

## Kendini kontrol et

??? question "CSI algılama için icat edilmiş bir ölçüm müdür?"
    Hayır. Alıcı paketi çözebilmek için kanalı zaten kestirir. CSI bu kestirimin
    dışarı verilmiş hâlidir.

??? question "80 MHz VHT kaydında 256 değer varken neden 242 alt taşıyıcı kullanılır?"
    Kalan kutular DC ve kenar korumasıdır; sinyal taşımazlar. Analizde ilk
    kontrol edilmesi gereken şeylerden biridir.

??? question "2 verici ve 4 alıcı antenli bir bağlantıda paket başına kaç kanal ölçülür?"
    Her alt taşıyıcı için 2 × 4 = 8.
