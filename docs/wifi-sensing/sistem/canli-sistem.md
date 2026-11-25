# 21 · Canlı sistem (bitirme projesi)

!!! info "Durum: taslak"

**Ön koşul:** Bütün modüller

**Bu modülün sonunda:**

- Zyxel cihazından CSI'yi canlı akıtan, temizleyen, karar veren ve sonucu
  tarayıcıda gösteren bir sistemi uçtan uca kendin kurmuş olursun.
- Kalibrasyon, etiketli kayıt toplama ve modeli yeniden eğitme döngüsünü işletebilirsin.
- Sistemin gecikmesini, yanlış alarm oranını ve kararlılığını ölçebilirsin.

## Konular

- Mimari: cihazda akış betiği → SSH → sunucu → pencereleme → model → tarayıcı paneli
- Kayıt oturumu protokolü: kanal ve bant kontrolü, trafik üretimi, etiket zamanlaması
- Boş oda kalibrasyonu ve ne zaman yenileneceği
- Nedensel karar: son N saniyelik geçmişle her birkaç saniyede bir tahmin
- Modelin sürümlenmesi, eğitim raporları, geri dönüş
- İzleme: paket hızı, kayıp, model güveni

## Kaynaklar

- Özel kaynak: wifi-sensing projesindeki canlı sistem kodları (sunucu, kayıt betikleri)
- Özel kaynak: Zyxel komut rehberi ve MediaTek CSI spesifikasyonu

## Kod alıştırmaları

1. Kaydedilmiş bir dosyayı canlı akış gibi oynatan bir simülatör yaz.
2. Bu akış üzerinde modül 11–12'deki modelleri gerçek zamanlı çalıştır.
3. Sonucu sunucudan tarayıcıya ileten basit bir panel kur.
4. Gerçek cihaza bağlan; bir hafta boyunca yanlış alarm günlüğü tut ve raporla.

## Kendini kontrol et

??? question "Canlı sistemde neden yalnızca geçmiş veriye bakan (nedensel) pencereler kullanılır?"
    Gerçek zamanda gelecek veri yoktur. Değerlendirmede gelecekten bilgi
    kullanmak, sahada tutmayacak bir başarı gösterir.
