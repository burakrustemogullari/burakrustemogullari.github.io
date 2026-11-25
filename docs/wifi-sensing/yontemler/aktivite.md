# 14 · Aktivite tanıma

!!! info "Durum: taslak"

**Ön koşul:** [12 · Varlık algılama](varlik.md), [9 · Temizleme](../veri/temizleme.md)

**Bu modülün sonunda:**

- Aktivitelerin CSI'de Doppler profili olarak nasıl ayrıştığını açıklayabilirsin.
- Faz temizlenmiş CSI'den Doppler spektrumu çıkaran bir pipeline yazabilirsin.
- Ortam ve kişi değişince başarının neden düştüğünü ölçebilirsin.

## Konular

- Aktivite sınıfları ve etiketleme
- Doppler tabanlı öznitelikler: spektrogram, Doppler profili, hız dağılımı
- Geniş bant ve çok antenin etkisi (160 MHz, 4 anten)
- Ortamdan ve kişiden bağımsız tanıma
- Derin öğrenme modelleri: CNN, zaman serisi ağları
- Algılamanın gerçek sınırları: hangi aktiviteler birbirine karışıyor

## Makale kartları

!!! note "Doldurulacak"
    Bu iki makale okundukça kartları tamamlanacak: problem, veri ve donanım,
    öznitelik, yöntem, sonuç, sınırlar, yeniden üretim.

- **01 · Exposing the CSI (2023):** CSI tabanlı algılamanın yetenek ve sınırlarının
  sistematik incelemesi. Veri: Asus RT-AX86U, 160 MHz, S1–S7 ortamları.
- **02 · SHARP (2021):** Ticari 802.11ac erişim noktalarıyla ortam ve kişiden
  bağımsız aktivite tanıma. Veri: Asus RT-AC86U + nexmon, 80 MHz.

## Kaynaklar

- [Makaleler: 01, 02](../ekler/makaleler.md#okuma-sirasi)
- Veri: Exposing-CSI, SHARP — [Ekler · Veri kümeleri](../ekler/veri-kumeleri.md)
- Özel kaynak: Wi-Fi Algılama Laboratuvarı, insan aktivite tanıma bölümü

## Kod alıştırmaları

1. SHARP kaydında anten oranıyla fazı temizle ve Doppler spektrogramı çıkar.
2. Doppler profillerinden basit öznitelikler (enerji, ortalama hız) hesaplayıp
   bir sınıflandırıcı eğit.
3. Küçük bir CNN eğit; bir ortamı dışarıda bırakıp test et.

## Kendini kontrol et

??? question "Aktivite tanımada genlik yerine Doppler'ın tercih edilmesinin nedeni nedir?"
    Doppler hız bilgisini taşır ve statik ortamdan büyük ölçüde bağımsızdır;
    genlik ise odanın yerleşimine sıkı sıkıya bağlıdır.
