# Veri kümeleri

Alıştırmalarda kullanılan veri kümeleri. Ham veri sitede ya da Git'te tutulmaz;
her biri kendi kaynağından indirilir ve **kendi lisansıyla** kullanılır.
Kullanırken ilgili makaleye atıf yapmak gerekir.

| Veri kümesi | Donanım | Görev ve etiket | Format | Boyut | Lisans |
|---|---|---|---|---|---|
| [MathWorks örneği](https://www.mathworks.com/help/wlan/ug/detect-human-presence-using-wireless-sensing-with-deep-learning.html) | ADALM-Pluto SDR, beacon | Boş oda / yürüme | `.mat` | ~2 MB | MathWorks koşulları |
| [SHARP](https://github.com/signetlabdei/SHARP) ([veri](https://researchdata.cab.unipd.it/624/)) | Asus RT-AC86U + nexmon, 80 MHz, 4 anten | Aktivite (boş, yürüme, koşma, zıplama, …) | `.mat` | ~6 GB | ODC-By |
| [Exposing the CSI](https://zenodo.org/records/7732595) | Asus RT-AX86U, 160 MHz, 4 anten, 150 paket/s | 7 ortam × 3 alıcı × 12 aktivite (boş dahil) | `.mat` | ~77 GB | Kaynaktaki lisans |
| [OpenCSI](https://zenodo.org/records/19861032) ([makale](https://arxiv.org/abs/2607.26665)) | ESP32 (3 nesil), 3 oda | Boş / dolu | `.h5` | ~3 GB | CC BY 4.0 |
| [Presence 2020](https://zenodo.org/records/3677366) | 30 alt taşıyıcı | İki kişi: durgun, hareketli, giriş, çıkış | gzip JSON | 28 GB (alt küme yeterli) | CC BY 4.0 |
| [Home](https://sdp8.org/Dataset?id=787a9a88-d2f3-4944-a174-8edf6070c99a) / [Office](https://sdp8.org/Dataset?id=277beeba-afdc-4bb1-8b47-88fa366fb27d) (SDP yarışması) | 4 anten, 64 alt taşıyıcı | Her 2 s'de kişi sayısı | metin | ~1,5 / ~4 GB | CC BY-NC-SA |
| Zyxel Wi-Fi 6 (kendi kayıtlarımız) | Zyxel EX5601-T0 (MediaTek MT7986A), 80/160 MHz, 2×4 anten | Boş oda, yürüme, oturma | JSON | ~0,7 GB | Özel, yayınlanmıyor |

## Önerilen sıra

1. **MathWorks:** Küçük ve iki sınıflı. İlk okuyucu ve ilk hareket dedektörü için ideal.
2. **SHARP:** Çok anten ve Doppler. Temizleme ve aktivite modülleri için.
3. **OpenCSI:** Ucuz ESP32 donanımı ve birden çok oda. Varlık ve genelleme için.
4. **Home/Office:** Kişi sayısı etiketleri. Çoklu kişi modülü için.
5. **Exposing the CSI:** En kapsamlısı ama çok büyük. Önce tek bir ortamı indir.
6. **Zyxel kayıtları:** Her modülün son alıştırması; yöntemin kendi ortamında çalışıp çalışmadığını gösterir.

## Kayıt tutma kuralları

- Ham dosyaları asla değiştirme; dönüştürülmüş veriyi ayrı klasöre yaz.
- Her dönüşüm için kaynak dosya, sürüm ve ayarları bir manifest dosyasına kaydet.
- Bir kaydın şüpheli bölümlerini silme; nedeniyle birlikte işaretle.
