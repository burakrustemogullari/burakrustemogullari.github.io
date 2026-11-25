# 12 · Varlık algılama

!!! info "Durum: taslak"

**Ön koşul:** [11 · Hareket algılama](hareket.md)

**Bu modülün sonunda:**

- Hareketi değil varlığı (duran kişi dahil) algılamanın neden daha zor olduğunu açıklayabilirsin.
- Boş oda profiline dayalı bir anomali dedektörü (KDE + eşik) yazabilirsin.
- Etiketli veriyle SVM sınıflandırıcı kurup grup-ayrık değerlendirebilirsin.
- Boş / duran / hareketli olmak üzere üç sınıflı bir model tasarlayabilirsin.

## Konular

- Varlık ile hareketin farkı; duran kişinin izi (nefes, bedenin statik etkisi)
- Boş oda kalibrasyonu ve ortam değişince kalibrasyonun eskimesi
- Pilot yaklaşımı: normal profil korelasyonu, çekirdek yoğunluk tahmini, $\beta$ eşiği
- SVM+CSI yaklaşımı: SNR (dB), DBSCAN ile gürültü temizliği, PCA, RBF çekirdekli SVM
- Kapı ve koridor etkisi: odanın dışındaki hareketin yanlış alarm üretmesi
- Nedensel değerlendirme: yalnız geçmiş pencereye bakarak karar vermek

## Makale kartları

**Pilot (2013), anomali tespiti kısmı**

| | |
|---|---|
| Öznitelik | Her paketin boş oda profiliyle ortalama korelasyonu |
| Yöntem | Normal profil dağılımı Gauss değil; Epanechnikov çekirdekli KDE, Scott bant genişliği; alt yüzdelik eşiği $\beta$ |
| Sonuç | Yüksek yanlış alarm aralığında RSS tabanlı RASID'i belirgin şekilde geçiyor |

**SVM ve CSI parmak izi (2017), varlık kısmı**

| | |
|---|---|
| Veri ve donanım | 2 yönlendirici + 2 Intel 5300 alıcı; laboratuvar (7×6 m) ve toplantı odası (6×6 m) |
| Yöntem | DBSCAN ile gürültü temizliği → PCA (360 → 93 boyut) → RBF çekirdekli SVM |
| Sonuç | Duran ve yürüyen kişide %97'nin üstünde doğruluk; RSSI'ya göre %10–24 daha iyi |
| Sınırlar | Aynı odada eğitilip test edilmiş; makaledeki FP/FN tanımları ters yazılmış |

## Kaynaklar

- Pilot ve SVM+CSI: [Makaleler](../ekler/makaleler.md)
- Veri: OpenCSI (ESP32, boş/dolu), Home/Office (SDP yarışması), presence_2020 —
  [Ekler · Veri kümeleri](../ekler/veri-kumeleri.md)

## Kod alıştırmaları

1. Boş oda kaydından normal profil çıkar; KDE ile yoğunluğu tahmin et; yeni
   pencereleri $\beta$ eşiğiyle sınıflandır.
2. OpenCSI üzerinde PCA + SVM sınıflandırıcı kur; odaları gruplayarak değerlendir.
3. Bir odada eğitip diğer odada test et; başarı düşüşünü raporla.
4. Zyxel kayıtlarında boş / duran / hareketli üç sınıflı bir model dene.

## Kendini kontrol et

??? question "Boş oda kalibrasyonu neden zamanla eskir?"
    Mobilya yer değiştirir, kapı açık ya da kapalı kalır, sıcaklık ve nem değişir.
    Statik bileşen değişince "normal" profil artık doğru değildir.

??? question "Varlık algılamada rastgele pencere bölmesi neden iyimser sonuç verir?"
    Aynı kayıttan komşu pencereler hem eğitimde hem testte bulunur.
