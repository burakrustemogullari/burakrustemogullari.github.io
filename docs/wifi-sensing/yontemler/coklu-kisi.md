# 18 · Çoklu kişi ve kalabalık sayımı

!!! info "Durum: taslak"

**Ön koşul:** [14 · Aktivite tanıma](aktivite.md), [13 · Pasif konumlama](konumlama.md)

**Bu modülün sonunda:**

- Birden çok kişinin etkilerinin CSI'de neden üst üste bindiğini açıklayabilirsin.
- 0 / 1 / 2+ kişi sayımı için bir model kurup değerlendirebilirsin.
- CSI ile kamera gibi başka modaliteleri zaman eşleyip etiket üretmenin yollarını anlatabilirsin.

## Konular

- Çoklu kişinin izi: Doppler bileşenlerinin karışması, kaynak ayırma (ICA)
- Kalabalık sayımı ve doluluk tahmini
- Kişi başına aktivite tanıma
- Çok modlu veri kümeleri: CSI, kamera, mmWave radar, LiDAR
- CSI–kamera senkronizasyonu ve otomatik etiketleme

## Makale kartları

!!! note "Doldurulacak"
    - **04 · WiMANS:** Wi-Fi ile çok kullanıcılı aktivite algılama için bir veri kümesi.
    - **05 · MM-Fi:** Çok modlu, temassız 4B insan veri kümesi.

    Kartlar makaleler okundukça tamamlanacak.

## Kaynaklar

- [Makaleler: 04, 05](../ekler/makaleler.md#okuma-sirasi)
- Veri: Home/Office (kişi sayısı etiketli) — [Ekler · Veri kümeleri](../ekler/veri-kumeleri.md)

## Kod alıştırmaları

1. Home/Office verisinde 0 / 1 / 2+ kişi sınıflandırıcısı eğit; kayıt grubu bazında değerlendir.
2. Sentetik iki yansıtıcıyla farklı hızlarda Doppler üret; ICA ile ayırmayı dene.
3. Kendi kayıtlarında kamera ve CSI zaman damgalarını eşleyen bir betik yaz.

## Kendini kontrol et

??? question "Kişi sayısı arttıkça sayım neden zorlaşır?"
    Etkiler toplanır ve doyuma ulaşır. 3 ile 4 kişinin yarattığı değişim,
    0 ile 1 arasındaki fark kadar belirgin değildir.
