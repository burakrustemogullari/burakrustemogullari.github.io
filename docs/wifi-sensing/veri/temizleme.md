# 9 · Temizleme

!!! info "Durum: taslak"

**Ön koşul:** [8 · Kayıt kalitesi](kayit-kalitesi.md)

**Bu modülün sonunda:**

- Ham fazın neden doğrudan kullanılamadığını formülle açıklayabilirsin.
- Faz sanitizasyonu, konjuge çarpım ve CSI oranı yöntemlerini uygulayıp karşılaştırabilirsin.
- Hampel süzgeci, bant geçiren süzgeç, arka plan çıkarma ve PCA ile sinyali hazırlayabilirsin.
- Hangi temizleme adımının hangi uygulamaya uygun olduğunu seçebilirsin.

## Konular

- Ölçülen faz: $\hat\varphi_k = \varphi_k - 2\pi k \Delta f \delta_t + \beta + Z_k$;
  zamanlama hatası (eğim) ve frekans kayması (sabit)
- Faz sanitizasyonu: unwrap ve alt taşıyıcı ekseninde doğrusal uydurma
- Konjuge çarpım $H_1 H_2^*$ ve CSI oranı $H_1/H_2$: antenlerde ortak hatanın silinmesi
- Genlik normalizasyonu ve AGC düzeltmesi
- Aykırı değerler: Hampel süzgeci (medyan ve MAD)
- Süzgeçler: Butterworth ve FIR; solunum, kalp ve yürüme bantları
- Arka plan (statik bileşen) çıkarma: boş oda ölçümü ya da yüksek geçiren süzgeç
- PCA ve ICA ile gürültü azaltma ve kaynak ayırma
- Alt taşıyıcı ve anten seçimi; LiFS'in "temiz alt taşıyıcı" seçimi

## Kaynaklar

- Özel kaynak: Wi-Fi Algılama Laboratuvarı, T6 bölümü
- LiFS makalesi (alt taşıyıcı seçimi): [Makaleler](../ekler/makaleler.md#lifs)
- SVM+CSI makalesi (DBSCAN ile gürültü temizliği, PCA):
  [Makaleler](../ekler/makaleler.md#svm-csi)

## Kod alıştırmaları

1. Art arda iki paketin ham fazını çiz; kanal değişmediği hâlde neden ilişkisiz
   olduklarını göster. Ardından doğrusal uydurma ile temizle.
2. İki alıcı antenli bir kayıtta konjuge çarpım ve CSI oranını hesapla; ham fazla
   karşılaştır.
3. Hampel süzgecini kendin yaz ve hazır bir uygulamayla aynı sonucu verdiğini doğrula.
4. Bir yürüme kaydında 2–80 Hz bant geçiren süzgeç, bir nefes simülasyonunda
   0,1–0,6 Hz süzgeç uygula; öncesini ve sonrasını çiz.
5. Alt taşıyıcı genlikleri üzerinde PCA uygula; ilk bileşeni atınca ne değiştiğini göster.

## Kendini kontrol et

??? question "Konjuge çarpım neden aynı çipteki iki antende işe yarar da farklı cihazlarda yaramaz?"
    Aynı çipteki antenler aynı osilatörü paylaşır; rastgele faz hatası ikisinde
    aynıdır ve çarpımda birbirini götürür.

??? question "Hampel süzgecinin penceresi olaydan uzunsa ne olur?"
    Kısa olaylar da aykırı değer sanılıp silinebilir.
