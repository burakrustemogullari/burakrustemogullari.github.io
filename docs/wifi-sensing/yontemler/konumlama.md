# 13 · Pasif konumlama

!!! info "Durum: taslak"

**Ön koşul:** [12 · Varlık algılama](varlik.md), [5 · Doppler ve Fresnel](../temeller/doppler-fresnel.md)

**Bu modülün sonunda:**

- Parmak izi (fingerprinting) ile model tabanlı konumlamanın farkını ve maliyetini açıklayabilirsin.
- Parmak izi veritabanı üzerinde MAP ve SVM regresyonu ile konum kestirebilirsin.
- LiFS'in güç sönümleme modeline dayalı denklem sistemini kurup çözebilirsin.
- Konum hatasını ortalama ve yüzdelik değerlerle raporlayabilirsin.

## Konular

- Sensing zone ve dead spot: bir bağlantının görebildiği bölge
- Parmak izi yaklaşımı: referans noktalarda ölçüm, eşleştirme; veritabanının eskimesi
- Sınıflandırma (nokta seçme) ile regresyon (koordinat kestirme)
- Model tabanlı yaklaşım: yayılım kaybı, Fresnel kırınımı, gövde emilimi
- Temiz alt taşıyıcı seçimi; doğrusal olmayan en küçük kareler (Levenberg–Marquardt),
  genetik algoritma + gradyan inişi
- Birden çok bağlantı, bilinmeyen verici konumları, denklem ve bilinmeyen sayısı

## Makale kartları

**Pilot (2013), konum kısmı:** Pasif radyo haritası (kişi her referans noktada
dururken alınan parmak izleri), korelasyon üzerinde KDE ve MAP; 2–4 bağlantıyla
laboratuvarda %90–98 doğru nokta.

**SVM ve CSI parmak izi (2017), konum kısmı:** Koordinatlar için iki ayrı ν-SVR;
ortalama hata 1,22 m ve 1,39 m. Regresyon, sınıflandırma ve Bayes yaklaşımlarından
yaklaşık %40 daha iyi.

**LiFS (2018):** Eğitimsiz, model tabanlı. Çok yollu yayılımdan etkilenmeyen
alt taşıyıcıları seçip güç sönümleme denklemlerini çözer. Medyan hata LoS'ta
0,5 m, NLoS'ta 1,1 m. Gereken tek kalibrasyon boş ortam ölçümüdür.

## Kaynaklar

- [Makaleler: Pilot, SVM+CSI, LiFS](../ekler/makaleler.md)
- Özel kaynak: Wi-Fi Algılama Laboratuvarı, pasif konumlama bölümü (U10)

## Kod alıştırmaları

1. Sentetik bir odada 20 referans noktası için CSI parmak izi üret (modül 3–5
   simülatörü); MAP ile en yakın noktayı bul.
2. Aynı veride SVR ile koordinat kestir; hatayı CDF olarak çiz.
3. Tek bir bağlantı için LiFS'in güç sönümleme modelini yaz; kişiyi LoS boyunca
   gezdirip teorik eğriyi çiz.
4. Dört AP'li sentetik düzende denklem sistemini en küçük karelerle çöz.

## Kendini kontrol et

??? question "Parmak izi yaklaşımının en büyük pratik maliyeti nedir?"
    Her referans noktada ölçüm toplamak ve ortam değiştikçe veritabanını yenilemek.

??? question "LiFS bilinmeyen verici konumlarını neden çözebilir?"
    Bağlantı (denklem) sayısı cihaz sayısıyla karesel, bilinmeyen sayısı ise
    doğrusal artar. Yeterli bağlantıda denklem sayısı bilinmeyenleri aşar.
