# 0 · Kurulum

!!! info "Durum: taslak"

**Ön koşul:** Temel Python (liste, döngü, fonksiyon) ve komut satırı.

**Bu modülün sonunda:**

- Çalışan bir Python ortamın ve Jupyter defterin olur.
- numpy dizileriyle karmaşık sayı tutup grafik çizebilirsin.
- Veri kümelerini nereye ve nasıl indireceğini bilirsin.

## Konular

- Python 3 ve sanal ortam (`venv`) kurmak
- Kütüphaneler: `numpy`, `scipy`, `matplotlib`, `scikit-learn`, `h5py`, `jupyterlab`;
  ileride derin öğrenme için `torch`
- Proje klasör düzeni: `data/` (ham veri, Git'e girmez), `notebooks/`, `src/`
- numpy'ye hızlı giriş: dizi şekli (`shape`), eksenler, karmaşık sayı tipi (`complex64`),
  yayın (broadcasting)
- matplotlib ile çizgi grafiği, ısı haritası (`imshow`), spektrogram
- Büyük veriyle çalışma alışkanlıkları: ham veriyi değiştirmemek, ara çıktıları
  ayrı kaydetmek, her deneyin ayarlarını yazmak

## Kaynaklar

- numpy başlangıç kılavuzu: <https://numpy.org/doc/stable/user/absolute_beginners.html>
- Veri kümelerinin listesi ve lisansları: [Ekler · Veri kümeleri](../ekler/veri-kumeleri.md)

## Kod alıştırmaları

1. Ortamı kur, bir Jupyter defteri aç ve kütüphane sürümlerini yazdır.
2. `(4, 2, 256, 500)` şeklinde rastgele karmaşık bir dizi oluştur (alıcı anten ×
   verici anten × alt taşıyıcı × zaman). Bir anten çifti için genliği
   alt taşıyıcı × zaman ısı haritası olarak çiz.
3. Aynı dizide ortalamayı farklı eksenler boyunca al ve çıkan şekilleri açıkla.

## Kendini kontrol et

??? question "Bir dizide `axis=-1` boyunca ortalama almak ne demek?"
    Son eksen boyunca, yani bu örnekte zaman boyunca ortalamak demektir.
    Sonuç `(4, 2, 256)` şeklinde olur.

??? question "Ham veriyi neden Git'e koymuyoruz?"
    Boyutu çok büyüktür ve çoğu veri kümesinin kendi lisansı vardır.
    Git'te yalnızca indirme ve hazırlama betikleri tutulur.
