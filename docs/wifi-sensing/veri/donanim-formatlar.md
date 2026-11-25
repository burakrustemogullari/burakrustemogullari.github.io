# 7 · Donanım ve kayıt formatları

!!! info "Durum: taslak"

**Ön koşul:** [A · Temeller](../temeller/index.md) bölümünün tamamı

**Bu modülün sonunda:**

- CSI veren başlıca donanımları ve aralarındaki farkları (bant, anten, alt taşıyıcı sayısı) sayabilirsin.
- Farklı kaynaklardan gelen kayıtları ortak bir diziye `(Nrx, Ntx, Nsc, T)` ve
  zaman damgası dizisine çeviren okuyucular yazabilirsin.
- Bir kaydın meta verisini (bant genişliği, kanal, anten zinciri, RSSI) okuyup yorumlayabilirsin.

## Konular

- Araçlar ve kartlar:
    - Linux 802.11n CSI Tool (Intel 5300): 30 alt taşıyıcı grubu, eski makalelerin çoğu
    - Atheros CSI Tool: OpenWrt yönlendiriciler
    - nexmon_csi (Broadcom): Raspberry Pi, Asus RT-AC86U; 80 MHz'e kadar
    - ESP32 esp-csi: ucuz, tek anten, HT20; yeni çiplerde 802.11ax
    - PicoScenes: Intel AX200/AX210, 160 MHz, yazılım tanımlı radyolar
    - Zyxel EX5601-T0 / MediaTek MT7986A: kendi kayıtlarımız
- Dosya biçimleri: MATLAB `.mat`, HDF5 `.h5`, CSV, JSON satırları; sıkıştırılmış akışlar
- Alt taşıyıcı sıralaması ve gruplama; kayıtta DC ve koruma kutularının yeri
- Zyxel JSON kaydı: zaman damgası, MAC, RSSI, SNR, bant genişliği kodu, hız modu,
  anten zinciri bilgisi, I ve Q dizileri
- Ortak format fikri: her kaynağı aynı dizi şekline ve aynı meta veri alanlarına çevirmek

## Kaynaklar

- Linux 802.11n CSI Tool: <http://dhalperi.github.io/linux-80211n-csitool/>
- nexmon_csi: <https://github.com/seemoo-lab/nexmon_csi>
- ESP32 esp-csi: <https://github.com/espressif/esp-csi>
- PicoScenes: <https://ps.zpj.io>
- Veri kümeleri ve formatları: [Ekler · Veri kümeleri](../ekler/veri-kumeleri.md)
- Özel kaynak: MediaTek Wi-Fi 7 CSI Spec v1.3 (JSON alanları) ve Zyxel komut rehberi

## Kod alıştırmaları

1. **MathWorks okuyucu:** Küçük `.mat` örneğini oku; 52 alt taşıyıcıyı ve zaman
   damgalarını diziye çevir. İlk veri kümesi olarak en kolayı budur.
2. **SHARP okuyucu:** `.mat` dosyasından 4 anten × 256 kutuyu oku, 242 kullanılan
   alt taşıyıcıyı ayır.
3. **OpenCSI okuyucu:** ESP32 `.h5` kayıtlarını oku; aynı dosyada farklı
   bant genişliğindeki paketleri ayırt et.
4. **Zyxel okuyucu:** JSON kaydındaki her paketi alanlarına ayır, I/Q'dan karmaşık
   CSI oluştur, anten zincirlerini `(Nrx, Ntx)` eksenlerine yerleştir.
5. Dört okuyucunun çıktısını aynı fonksiyonla çizdir: bir anten çifti için
   alt taşıyıcı × zaman genlik ısı haritası.

## Kendini kontrol et

??? question "Intel 5300 ile toplanmış bir veri kümesinde neden 30 alt taşıyıcı vardır?"
    Kart 20 MHz'deki 56 alt taşıyıcıyı gruplayarak yaklaşık ikide birini raporlar.

??? question "Zyxel cihazında CSI hangi paketlerden ölçülür? Bu neden önemlidir?"
    AP'nin aldığı çerçevelerden. İstemci trafik göndermiyorsa ölçüm de yoktur;
    ping ya da iperf ile trafik üretmek gerekir.
