# 1 · Matematik araç kutusu

!!! info "Durum: taslak"

**Ön koşul:** [0 · Kurulum](../baslangic/kurulum.md)

**Bu modülün sonunda:**

- Bir sinüs dalgasını genlik, frekans ve fazıyla tanımlayabilirsin.
- Karmaşık sayıyı bir fazör (dönen ok) olarak düşünüp genlik ve fazı ondan çıkarabilirsin.
- Desibel ile doğrusal güç arasında geçiş yapabilirsin.
- FFT ile bir sinyalin içindeki frekansları bulabilirsin.
- Korelasyon, kovaryans matrisi, özdeğer ve PCA'nın ne ölçtüğünü açıklayabilirsin.

## Konular

- Salınım: periyot, frekans, açısal frekans $\omega = 2\pi f$, genlik
- Faz: tur, derece, radyan; faz sarılması ve sarılmanın açılması (unwrap)
- Karmaşık sayı: $z = I + jQ = |z|e^{j\varphi}$; çarpma = boyları çarp, açıları topla;
  eşlenik (konjuge) ile açı farkı almak
- Fazör: $A\cos(\omega t + \varphi)$ sinyalini $Ae^{j\varphi}$ ile temsil etmek
- Desibel: güç için $10\log_{10}$, genlik için $20\log_{10}$; dBm
- Fourier ve FFT: frekans çözünürlüğü $1/T$, örnekleme frekansı ve Nyquist sınırı,
  pencereleme, STFT ve spektrogram
- İstatistik: ortalama, varyans, standart sapma, medyan ve MAD, korelasyon katsayısı
- Doğrusal cebir: kovaryans matrisi, özdeğer ve özvektör, PCA

## Kaynaklar

- Özel kaynak: Wi-Fi Algılama Laboratuvarı, T0 bölümü (yayınlanmıyor)
- FIMD makalesinin özdeğer özniteliği bu modüldeki doğrusal cebiri kullanır:
  [Makaleler](../ekler/makaleler.md#fimd)

## Kod alıştırmaları

1. 3 Hz'lik, 40° fazlı bir kosinüs üret. Aynı sinyali bir fazörle yeniden kur
   ve iki eğrinin örtüştüğünü göster.
2. Rastgele fazlı 5 fazörü topla; sonucun genlik ve fazını hem elle hem numpy ile hesapla.
3. 0,25 Hz (nefes) ve 1,2 Hz (kalp) bileşenli gürültülü bir sinyal üret. FFT ile
   iki tepeyi bul; kayıt süresini kısaltınca çözünürlüğün nasıl bozulduğunu göster.
4. 30 boyutlu, birbiriyle ilişkili sentetik bir veri üret. PCA uygula ve ilk
   bileşenin varyansın ne kadarını taşıdığını hesapla.

## Kendini kontrol et

??? question "İki karmaşık sayıyı çarpınca fazları ne olur? Birini diğerinin eşleniğiyle çarpınca?"
    Çarpmada fazlar toplanır. Eşlenikle çarpmada fazlar çıkarılır; sonuçta
    yalnızca iki fazın farkı kalır.

??? question "10 saniyelik bir kayıtta FFT'nin frekans çözünürlüğü nedir?"
    $1/10 = 0{,}1$ Hz.

??? question "Gücü 2 katına çıkan bir sinyal kaç dB artar?"
    Yaklaşık 3 dB.
