# 15 · Solunum ve kalp atışı

!!! info "Durum: taslak"

**Ön koşul:** [12 · Varlık algılama](varlik.md), [9 · Temizleme](../veri/temizleme.md)

**Bu modülün sonunda:**

- Milimetrelik göğüs hareketinin fazda nasıl bir salınım yarattığını hesaplayabilirsin.
- Anten oranı fazı + bant geçiren süzgeç + spektrum tepesi ile nefes hızı kestirebilirsin.
- Sonucu bir referans sensörle karşılaştırıp hata raporlayabilirsin.

## Konular

- Göğüs ve kalp hareketinin genliği; 5 GHz'de faz karşılığı
- Fresnel konumuna göre görünürlük ve alt taşıyıcı seçimi
- Süzgeç bantları: solunum 0,1–0,6 Hz, kalp 0,8–2 Hz
- Spektrum tepesi, otokorelasyon ve tepe sayma yöntemleri
- Kalp atışının solunum harmoniklerinden ayrılması
- Gerçek zamanlı çalışma: pencere uzunluğu ve gecikme dengesi
- Referans ölçüm (göğüs kemeri, nabız ölçer) ile karşılaştırma

## Makale kartı

!!! note "Doldurulacak"
    **09 · WiFi-based Real-time Breathing and Heart Rate Monitoring during Sleep (2019).**
    Kart makale okundukça tamamlanacak.

## Kaynaklar

- [Makaleler: 09](../ekler/makaleler.md#okuma-sirasi)
- Özel kaynak: Wi-Fi Algılama Laboratuvarı, solunum ve kalp atışı bölümü (U4)

## Kod alıştırmaları

1. Sentetik bir göğüs hareketini (0,25 Hz) simüle et ve CSI fazından nefes hızını kestir.
2. Zyxel kaydında anten oranı fazını hesapla, 0,1–0,6 Hz süzgeç uygula,
   spektrum tepesinden nefes/dakika çıkar.
3. Pencere uzunluğunu 10, 20 ve 30 s yapıp kestirim hatasını karşılaştır.

## Kendini kontrol et

??? question "Spektrum tepesi 0,3 Hz'de ise nefes hızı kaçtır?"
    0,3 × 60 = 18 nefes/dakika.

??? question "Kalp atışını ölçmek neden nefesten çok daha zordur?"
    Göğüsteki kalp hareketi çok daha küçüktür ve solunumun harmonikleri aynı
    frekans bandına düşebilir.
