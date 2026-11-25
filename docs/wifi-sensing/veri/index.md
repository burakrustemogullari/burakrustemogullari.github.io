# B · Gerçek CSI verisiyle çalışmak

Sentetik CSI temizdir; gerçek CSI değildir. Bu bölüm gerçek bir kaydı açmaktan
başlayıp ona güvenilir öznitelik çıkarmaya kadar giden yolu kurar. Alıştırmalar
önce açık veri kümeleriyle, sonra kendi Zyxel ve ESP32 kayıtlarıyla yapılır.

| Modül | Soru |
|---|---|
| [7 · Donanım ve kayıt formatları](donanim-formatlar.md) | CSI'yi hangi cihaz verir, dosyada nasıl durur? |
| [8 · Kayıt kalitesi](kayit-kalitesi.md) | Bu kayda güvenebilir miyim? |
| [9 · Temizleme](temizleme.md) | Donanımın eklediği hataları nasıl ayıklarım? |
| [10 · Öznitelik, karar ve değerlendirme](oznitelik-karar.md) | Temiz sinyalden nasıl karar çıkar, başarıyı nasıl dürüstçe ölçerim? |

**Bölüm sonu hedefi:** Herhangi bir desteklenen kaydı okuyan, kalite raporu
çıkaran, temizleyen ve pencere başına öznitelik tablosu üreten küçük bir
kütüphane (`okuyucu → kalite → temizle → öznitelik`).
