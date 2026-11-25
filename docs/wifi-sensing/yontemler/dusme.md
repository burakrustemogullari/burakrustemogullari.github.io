# 17 · Düşme algılama

!!! info "Durum: taslak"

**Ön koşul:** [14 · Aktivite tanıma](aktivite.md)

**Bu modülün sonunda:**

- Düşmeyi diğer hızlı hareketlerden (oturma, eğilme) ayıran sinyal özelliklerini sayabilirsin.
- Olay tabanlı değerlendirme yapabilirsin (pencere değil olay başına isabet ve yanlış alarm).
- Çevrimiçi (gerçek zamanlı) bir düşme dedektörünün tasarım kararlarını açıklayabilirsin.

## Konular

- Düşmenin izi: kısa süreli yüksek hız, ardından hareketsizlik
- Nadir olay problemi: dengesiz veri, yanlış alarmın maliyeti
- Anomali olarak düşme ile sınıf olarak düşme
- Olay tabanlı ölçütler: olay başına tespit, günlük yanlış alarm
- Gerçek zamanlı çalışma: tetikleme, onay penceresi, gecikme

## Makale kartı

!!! note "Doldurulacak"
    **08 · SiFall:** RF algılamayla pratik, çevrimiçi düşme tespiti.
    Kart makale okundukça tamamlanacak.

## Kaynaklar

- [Makaleler: 08](../ekler/makaleler.md#okuma-sirasi)
- Özel kaynak: Wi-Fi Algılama Laboratuvarı, düşme algılama bölümü

## Kod alıştırmaları

1. Bir aktivite veri kümesinde ani hız artışı + hareketsizlik kuralıyla basit bir dedektör yaz.
2. Pencere tabanlı ve olay tabanlı ölçütleri aynı sonuç için hesapla; farkı açıkla.
3. Güvenli koşullarda (minder üzerinde) kendi kontrollü kayıtlarını topla.

## Kendini kontrol et

??? question "Düşme algılamada neden düz doğruluk yerine olay başına yanlış alarm raporlanır?"
    Düşme nadirdir. Saatte birkaç yanlış alarm veren bir sistem doğruluğu yüksek
    görünse de pratikte kullanılamaz.
