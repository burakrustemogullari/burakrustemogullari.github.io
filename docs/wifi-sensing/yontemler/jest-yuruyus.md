# 16 · Jest ve yürüyüş tanıma

!!! info "Durum: taslak"

**Ön koşul:** [14 · Aktivite tanıma](aktivite.md), [6 · ToF, AoA ve MIMO](../temeller/tof-aoa-mimo.md)

**Bu modülün sonunda:**

- Konuma ve yöne bağlı Doppler'ı kişiye bağlı bir hız temsiline çevirme fikrini açıklayabilirsin.
- Hazır bir jest veri kümesinde öznitelik çıkarıp sınıflandırıcı eğitebilirsin.
- Yürüyüş desenlerinden kişi tanımanın gizlilik sonuçlarını tartışabilirsin.

## Konular

- Jest, aktiviteden daha kısa ve daha ince bir harekettir
- Alanlar arası (cross-domain) tanıma: konum, yön ve ortam değişince ne olur
- Kişi koordinatlarında hız profili fikri
- Yürüyüş biyometrisi: adım periyodu, kol ve bacak mikro-Doppler'ı
- Çok alıcılı düzenler ve bunların maliyeti

## Makale kartları

!!! note "Doldurulacak"
    - **06 · Widar3.0:** Wi-Fi ile sıfır çabayla alanlar arası jest tanıma.
    - **07 · GaitSense:** Wi-Fi ile yürüyüşe dayalı kişi tanıma.

    Kartlar makaleler okundukça tamamlanacak.

## Kaynaklar

- [Makaleler: 06, 07](../ekler/makaleler.md#okuma-sirasi)
- Widar3.0 veri kümesi: <https://tns.thss.tsinghua.edu.cn/widar3.0/>
- Özel kaynak: Wi-Fi Algılama Laboratuvarı, jest ve yürüyüş bölümleri

## Kod alıştırmaları

1. Widar3.0'ın hazır hız profillerinden küçük bir alt küme indir ve görselleştir.
2. Bir konumda eğitip başka konumda test eden bir jest sınıflandırıcısı kur.
3. Zyxel ile kendi basit jestlerini (el sallama, itme) kaydet ve aynı pipeline'ı dene.

## Kendini kontrol et

??? question "Aynı jest farklı konumda yapıldığında Doppler neden değişir?"
    Doppler, yol uzunluğunun değişim hızıdır ve bu hız kişinin verici ile alıcıya
    göre konumuna ve yönüne bağlıdır.
