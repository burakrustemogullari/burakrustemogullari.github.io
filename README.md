# Burak Rüstemoğulları — kişisel site

Portfolyo ve teknik notlar. [MkDocs](https://www.mkdocs.org/) +
[Material](https://squidfunk.github.io/mkdocs-material/) ile üretilen statik site.

## Yerelde çalıştırma

```bash
python3 -m venv .venv
.venv/bin/pip install -r requirements.txt
.venv/bin/mkdocs serve
```

Sonra <http://127.0.0.1:8000>. Dosyaları kaydettikçe tarayıcı kendiliğinden yenilenir.

## Yeni sayfa ekleme

1. İlgili klasörün altına `.md` dosyasını ekle (ör. `docs/wifi-sensing/`).

### Wi-Fi Sensing ders yapısı

`docs/wifi-sensing/` sıfırdan ileri düzeye bir ders akışıdır:
`baslangic/` (kurulum), `temeller/` (modül 1–6), `veri/` (7–10),
`yontemler/` (11–19), `sistem/` (20–21) ve `ekler/` (makaleler, veri
kümeleri, sözlük). Her bölümün `index.md` dosyası bölüm giriş sayfasıdır.
Modül sayfaları aynı şablonu izler: ön koşul, hedefler, konular, kaynaklar,
kod alıştırmaları, kendini kontrol et.
2. `mkdocs.yml` içindeki `nav` listesine bir satır yaz — sıralamayı bu belirler.
3. `mkdocs build --strict` ile kontrol et; kırık bağlantı varsa hata verir.

## Yapı

| Yol | İçerik |
| --- | --- |
| `docs/` | Tüm sayfalar (Markdown) |
| `docs/assets/` | Logo, vesikalık, şirket logoları |
| `docs/stylesheets/extra.css` | Tema renkleri, hero, zaman çizelgesi, kartlar |
| `overrides/main.html` | Sol menüye profil kartı ekleyen şablon |
| `mkdocs.yml` | Tema, menü, eklenti ayarları |
| `.github/workflows/deploy.yml` | `main`'e push'ta GitHub Pages'e yayın |

## Notlar

- Sürümler `requirements.txt` içinde sabit. Körlemesine yükseltme yapma;
  yükselttikten sonra `mkdocs build --strict` çalıştır.
- `overrides/main.html`, Material'ın `base.html` dosyasındaki `site_nav` bloğunun
  kopyasıdır. Material sürümünü yükseltirsen orijinaliyle karşılaştır.
