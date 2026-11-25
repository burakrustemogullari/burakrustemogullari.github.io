# 8 · Kayıt kalitesi

!!! info "Durum: taslak"

**Ön koşul:** [7 · Donanım ve kayıt formatları](donanim-formatlar.md)

**Bu modülün sonunda:**

- Bir kaydın gerçek paket hızını, zaman aralıklarını ve kayıplarını ölçebilirsin.
- Sıfır I/Q, eksik anten zinciri, AGC sıçraması ve sabit kutu gibi sorunları otomatik bulabilirsin.
- Her kayıt için yeniden üretilebilir bir kalite raporu çıkarabilirsin.

## Konular

- Wi-Fi'da paketler neden eşit aralıklı gelmez: CSMA/CA, çarpışma, yeniden gönderme
- Paket hızı, aralık dağılımı, boşluklar ve patlamalı (bursty) trafik
- Düzensiz zamanı eşit aralıklı ızgaraya taşımak: aradeğerleme ve sınırları
- Sıfır ya da sabit I/Q değerleri; DC ve koruma kutuları
- Otomatik kazanç kontrolü (AGC): genlikte basamaklar, RSSI ve kazanç alanlarıyla düzeltme
- Eksik ya da sırası belirsiz anten zincirleri
- Meta veri tutmak: kanal, bant genişliği, cihaz yerleşimi, oda, kişi, tarih, oturum kimliği
- Şüpheli bölümleri silmek yerine nedeniyle işaretlemek

## Kaynaklar

- Özel kaynak: Wi-Fi Algılama Laboratuvarı, T6 bölümü (zaman ve genlik hataları)
- Özel kaynak: wifi-sensing çalışma planı, faz 2 (ölçüm ve kayıt kalitesi)

## Kod alıştırmaları

1. Bir kaydın paket aralıklarının histogramını ve zaman içindeki paket hızını çiz.
2. Kalite fonksiyonu yaz: süre, paket sayısı, ortalama ve medyan hız, en uzun boşluk,
   sıfır I/Q oranı, sabit kutular, anten zinciri tamlığı. Sonucu sözlük olarak döndür.
3. Zyxel `bos_oda` kayıtlarının hepsi için raporu tek bir tabloda topla.
4. RSSI ile ortalama CSI genliğini aynı grafikte çiz; AGC sıçramalarını işaretle.
5. Kaydı 0,05 s'lik eşit ızgaraya taşı; büyük boşlukları aradeğerlemek yerine maskele.

## Kendini kontrol et

??? question "Paketler eşit aralıklı değilse doğrudan FFT almak neden yanlıştır?"
    FFT eşit örnekleme varsayar. Düzensiz örneklerde frekanslar yanlış yerde
    görünür ve spektrum bulanıklaşır.

??? question "Bir kaydın paket hızını neden ayardan değil zaman damgalarından okumalısın?"
    Gerçek hız trafiğe ve kanal yoğunluğuna bağlıdır; ayarlanan değerle
    çoğu zaman aynı değildir.
