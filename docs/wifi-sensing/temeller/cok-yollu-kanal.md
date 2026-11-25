# 3 · Çok yollu kanal

!!! info "Durum: taslak"

**Ön koşul:** [2 · Dalga, faz ve yol kaybı](dalga.md)

**Bu modülün sonunda:**

- Kanal dürtü yanıtını (CIR) ve kanal frekans yanıtını (CFR) tanımlayıp
  birinden ötekine geçebilirsin.
- Frekans seçici sönümlemenin neden oluştuğunu bir simülasyonla gösterebilirsin.
- Kanalı statik ve dinamik bileşenlere ayırmanın algılamadaki önemini açıklayabilirsin.

## Konular

- Neden içeride tek yol yoktur: doğrudan yol (LoS), duvar ve eşya yansımaları
- CIR: $h(\tau) = \sum_i a_i\,\delta(\tau - \tau_i)$; gecikme yayılımı
- CFR: $H(f) = \sum_i a_i\,e^{-j2\pi f \tau_i}$; Fourier ilişkisi
- Frekans seçici sönümleme ve tutarlılık bandı (coherence bandwidth)
- Statik bileşen $H_s$ ve insandan gelen dinamik bileşen $H_d(t)$: $H(f,t) = H_s(f) + H_d(f,t)$
- CFR'den IFFT ile gecikme profiline dönmek (Pilot makalesindeki fikir)

## Kaynaklar

- Özel kaynak: Wi-Fi Algılama Laboratuvarı, T2 bölümü
- Pilot makalesinin gecikme profili gözlemi: [Makaleler](../ekler/makaleler.md#pilot)

## Kod alıştırmaları

1. **Kanal simülatörü:** Yolların listesini (uzunluk, zayıflama) alıp verilen
   frekanslarda CFR döndüren bir fonksiyon yaz. Bu fonksiyonu sonraki modüllerde
   tekrar kullanacaksın.
2. Tek yol ile beş yol için 20 MHz bant boyunca $|H(f)|$'yi çiz; çukurları göster.
3. CFR'ye IFFT uygula ve yolların gecikmelerini geri bul. Bant genişliği
   20 MHz'den 160 MHz'e çıkınca yolların ne kadar ayrıştığını karşılaştır.
4. Statik yollara zamanla uzayan tek bir "insan" yolu ekle; $|H|$'nin zamanla
   nasıl salındığını çiz.

## Kendini kontrol et

??? question "RSSI neden çok yollu kanaldaki ayrıntıyı kaybeder?"
    Bütün frekanslardaki gücü tek bir sayıda toplar. Bir frekansta güç artıp
    diğerinde azalırsa toplam değişmeyebilir.

??? question "Gecikmeleri ayırma çözünürlüğü neye bağlıdır?"
    Bant genişliğine. Çözünürlük yaklaşık $1/B$'dir; 20 MHz'de 50 ns, yani
    yaklaşık 15 m yol farkı.
