# 10 · Öznitelik, karar ve değerlendirme

!!! info "Durum: taslak"

**Ön koşul:** [9 · Temizleme](temizleme.md)

**Bu modülün sonunda:**

- Pencereleme yapıp zaman, frekans ve istatistik öznitelikleri çıkarabilirsin.
- Eşik, yoğunluk tahmini, kümeleme ve sınıflandırıcıları ne zaman kullanacağını seçebilirsin.
- Veri sızıntısı olmadan eğitim/test bölmesi yapıp doğru ölçütlerle raporlayabilirsin.
- Alan kaymasının (oda, kişi, cihaz değişince) neden en büyük sorun olduğunu açıklayabilirsin.

## Konular

- Temel kavramlar: pencere, öznitelik, etiket, model; nedensel (yalnız geçmişe bakan) pencere
- Öznitelik aileleri:
    - istatistik: varyans, değişim katsayısı, korelasyon, özdeğer
    - frekans: bant gücü, spektral entropi, Doppler profili
    - öğrenilen: CNN ile ham tensörden
- Karar yöntemleri:
    - eşik ve kayan pencere
    - yoğunluk tahmini (KDE) ve anomali
    - DBSCAN
    - SVM sınıflandırma ve regresyon
    - CNN ve zaman serisi ağları
- Değerlendirme:
    - karmaşıklık matrisi, dengeli doğruluk, ROC ve AUC
    - yanlış alarm ve kaçırma oranı
    - konum için ortalama ve yüzdelik hata
- Bölme protokolleri: rastgele bölmenin tuzağı, kayıt ve oturum grupları,
  bir grubu dışarıda bırakma (leave-one-group-out)
- Alan kayması ve alan adaptasyonu; neden "başka odada" test şart

## Kaynaklar

- Özel kaynak: Wi-Fi Algılama Laboratuvarı, T7 bölümü
- 03 · Wi-Fi sensing genelleme taraması: [Makaleler](../ekler/makaleler.md#genelleme)

## Kod alıştırmaları

1. Bir kaydı 10 s'lik, %50 örtüşmeli pencerelere böl; her pencere için 5 öznitelik hesapla.
2. Aynı veride rastgele bölme ile kayıt-grubu bölmesini karşılaştır; doğruluk farkını açıkla.
3. Eşik tabanlı bir dedektör yaz ve ROC eğrisini çiz.
4. Aynı öznitelikler üzerinde lojistik regresyon ve SVM'i dengeli doğrulukla karşılaştır.

## Kendini kontrol et

??? question "Örtüşen pencereleri rastgele eğitim ve test kümelerine dağıtmak neden hatadır?"
    Komşu pencereler neredeyse aynı veriyi içerir. Test kümesi eğitim verisini
    görmüş olur ve başarı olduğundan yüksek çıkar.

??? question "Boş oda örnekleri %90 olan bir veri kümesinde neden düz doğruluk yanıltıcıdır?"
    Her şeye "boş" diyen bir model %90 doğruluk alır. Dengeli doğruluk ya da
    sınıf başına ölçütler gerekir.
