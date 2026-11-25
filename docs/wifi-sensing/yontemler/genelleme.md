# 19 · Genelleme ve alan adaptasyonu

!!! info "Durum: taslak"

**Ön koşul:** [14 · Aktivite tanıma](aktivite.md), [10 · Öznitelik, karar ve değerlendirme](../veri/oznitelik-karar.md)

**Bu modülün sonunda:**

- Alan kaymasının türlerini (ortam, kişi, cihaz, konum, zaman) sayabilirsin.
- Bir modelin genellemesini dürüstçe ölçen bir deney tasarlayabilirsin.
- Genellemeyi artıran başlıca teknik ailelerini ve ne zaman işe yaradıklarını açıklayabilirsin.

## Konular

- Wi-Fi sensing'in en büyük açık problemi: başka odada çalışmamak
- Alan kayması türleri ve ölçülmesi
- Ortamdan bağımsız temsiller: Doppler, hız profili, oran tabanlı öznitelikler
- Alan adaptasyonu, alan genelleme, az örnekle öğrenme
- Veri artırma ve sentetik veri
- Değerlendirme: kaynağı dışarıda bırakma (leave-one-source-out)

## Makale kartı

!!! note "Doldurulacak"
    **03 · A Survey on Wi-Fi Sensing Generalizability (2025):** Taksonomi, teknikler,
    veri kümeleri ve gelecek araştırma yönleri. Kart makale okundukça tamamlanacak.

## Kaynaklar

- [Makaleler: 03](../ekler/makaleler.md#genelleme)
- Genelleme kaynak listesi: <https://github.com/airslab2020/awesome-wireless-sensing-generalization>

## Kod alıştırmaları

1. Varlık modelini Home'da eğitip Office'te test et; sonra tersini yap.
2. Genlik öznitelikleri yerine anten oranı fazı kullan; düşüş azalıyor mu ölç.
3. Kaynağı dışarıda bırakma protokolünü bütün açık veri kümeleri için kur.

## Kendini kontrol et

??? question "Aynı odada %99 doğruluk veren bir model neden yeterli kanıt değildir?"
    Model odanın kendine özgü statik kanalını ezberlemiş olabilir. Başka odada
    ya da başka günde test edilmeden genelleme hakkında bir şey söylenemez.
