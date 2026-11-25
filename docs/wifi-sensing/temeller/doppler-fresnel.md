# 5 · Doppler ve Fresnel bölgeleri

!!! info "Durum: taslak"

**Ön koşul:** [4 · OFDM ve CSI](ofdm-csi.md)

**Bu modülün sonunda:**

- Hareketin hızından Doppler kaymasını hesaplayabilirsin.
- CSI zaman serisinden STFT ile spektrogram çıkarıp hareketi okuyabilirsin.
- Fresnel bölgelerini çizip bir kişinin neden bazı konumlarda kolay, bazılarında
  zor algılandığını açıklayabilirsin.

## Konular

- Doppler kayması: yol uzunluğunun değişim hızı / dalga boyu
- Yansıyan yolun hızı ile kişinin hızı arasındaki ilişki (bistatik geometri)
- Doppler spektrumu, mikro-Doppler (kol ve bacak hareketi)
- Ölçüm hızı ile ölçülebilir en büyük hız arasındaki ilişki
- Fresnel bölgeleri: verici ve alıcı odaklı elipsler, $r_1 = \sqrt{\lambda d_1 d_2 / d}$
- Algılanabilirlik ve kör noktalar; nefesin bazı konumlarda görünmemesi
- LiFS'in güç sönümleme modeli: LoS üstünde, birinci Fresnel bölgesi içinde, dışında

## Kaynaklar

- Özel kaynak: Wi-Fi Algılama Laboratuvarı, T4 bölümü
- LiFS makalesi: [Makaleler](../ekler/makaleler.md#lifs)

## Kod alıştırmaları

1. Modül 3'teki simülatörde bir yansıtıcıyı 1 m/s ile yürüt. CSI zaman serisinin
   spektrogramını çiz ve Doppler frekansını teorik değerle karşılaştır.
2. Göğüs hareketini (5 mm genlik, 0,25 Hz) simüle et. Kişiyi Fresnel sınırları
   boyunca kaydırıp genlik salınımının büyüklüğünü konuma göre çiz.
3. Verici–alıcı arası 6 m iken 5 GHz için ilk üç Fresnel elipsini çiz.

## Kendini kontrol et

??? question "Ölçüm hızı saniyede 100 paket ise ölçülebilecek en büyük Doppler frekansı nedir?"
    Nyquist sınırı nedeniyle 50 Hz (karmaşık örneklemede ±50 Hz).

??? question "Kişi verici–alıcı hattından uzaklaştıkça algılama neden zorlaşır?"
    Kişi Fresnel bölgelerinin dışına çıktıkça bağlantıya etkisi küçülür ve
    değişim gürültünün altında kalır.
