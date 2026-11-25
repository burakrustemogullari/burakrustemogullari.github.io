# 6 · ToF, AoA ve MIMO

!!! info "Durum: taslak"

**Ön koşul:** [5 · Doppler ve Fresnel bölgeleri](doppler-fresnel.md)

**Bu modülün sonunda:**

- Bir yolun uçuş süresini (ToF) alt taşıyıcılar arası faz eğiminden kestirmeyi anlatabilirsin.
- Anten dizisinde geliş açısını (AoA) antenler arası faz farkından hesaplayabilirsin.
- MUSIC algoritmasının mantığını ve sınırlarını açıklayabilirsin.
- MIMO'nun algılamaya katkılarını sayabilirsin.

## Konular

- ToF: gecikme ile alt taşıyıcı ekseninde doğrusal faz eğimi; çözünürlük ve bant genişliği
- AoA: düzgün doğrusal dizi, $\Delta\varphi = 2\pi d \sin\theta / \lambda$; AoD
- Faz dizisi ve hüzme oluşturma
- Alt uzay yöntemleri: MUSIC, 2B (ToF–AoA) kestirim
- Ticari kartlardaki sınırlar: az anten, faz kalibrasyonu ihtiyacı
- MIMO'nun üç katkısı: uzaysal çeşitlilik, açı bilgisi, antenler arası oranla faz temizleme

## Kaynaklar

- Özel kaynak: Wi-Fi Algılama Laboratuvarı, T5 bölümü
- Hands-on Wireless Sensing eğitimi, AoA ve ToF bölümleri:
  <https://tns.thss.tsinghua.edu.cn/wst/docs/intro/>

## Kod alıştırmaları

1. Üç yollu sentetik bir kanalda alt taşıyıcı fazlarından tek yolun ToF'unu kestir.
2. 3 antenli doğrusal bir dizi için sentetik CSI üret ve basit bir AoA taraması
   (Bartlett) yap.
3. Aynı veriye MUSIC uygula; iki yol birbirine yaklaşınca iki yöntemi karşılaştır.

## Kendini kontrol et

??? question "Antenler arası mesafe neden genellikle yarım dalga boyu seçilir?"
    Daha büyük aralıkta faz farkı ±180°'yi aşıp açılar birbirine karışır
    (uzaysal örtüşme).

??? question "Ticari Wi-Fi kartlarında AoA kestirimi neden zordur?"
    Anten sayısı azdır ve her zincirin bilinmeyen bir faz kayması vardır;
    kalibrasyon gerekir.
