# 11 · Hareket algılama

!!! info "Durum: taslak"

**Ön koşul:** [B · Gerçek veri](../veri/index.md) bölümünün tamamı

**Bu modülün sonunda:**

- Durgun ortamda CSI'nin kendisiyle yüksek korelasyonlu kaldığını kendi verinde gösterebilirsin.
- FIMD'nin özdeğer özniteliğini ve DBSCAN tabanlı kararını sıfırdan yazabilirsin.
- Yanlış alarm süzgecini ve birden çok bağlantının birleştirilmesini uygulayabilirsin.
- Sonucu ROC eğrisiyle RSSI tabanlı bir referansla karşılaştırabilirsin.

## Konular

- Hareketin CSI'de bıraktığı iz: korelasyonun düşmesi, varyansın artması
- Kayan pencerede paketler arası korelasyon matrisi ve en büyük özdeğer
- DBSCAN: `eps`, `minPts`, çekirdek nokta, aykırı nokta
- Yanlış alarm süzgeci: komşu pencerelerle tutarlılık
- Çok bağlantılı karar birleştirme (olabilirlik oranı)
- RSSI tabanlı referans: hareketli varyans

## Makale kartı: FIMD (2012)

| | |
|---|---|
| Problem | Cihaz taşımayan birinin hareketini Wi-Fi ile algılamak |
| Veri ve donanım | TP-Link yönlendirici (AP) + Intel 5300 kartlı laptop; tek anten; laboratuvar ve koridor |
| Öznitelik | $n$ paketlik pencerede korelasyon matrisinin normalize en büyük özdeğeri ($V \approx 1$ durgun, hareketle düşer) |
| Yöntem | 1. ve 2. özdeğer düzleminde DBSCAN; yanlış alarm süzgeci; bağlantılar arası birleştirme |
| Sonuç | Laboratuvarda %1 yanlış alarmda yaklaşık %70, %14'te %90'ın üstünde tespit; RSS tabanlı RASID'den biraz iyi |
| Sınırlar | Hareketsiz duran kişiyi görmez; eşikler ortama bağlı; makaledeki formüllerde yazım hataları var |
| Yeniden üretim | MathWorks (boş/yürüme) → Zyxel `bos_oda` / `yurume` |

## Kaynaklar

- FIMD: [Makaleler](../ekler/makaleler.md#fimd)
- Özel kaynak: Wi-Fi Algılama Laboratuvarı, hareket algılama bölümü (U2)

## Kod alıştırmaları

1. Boş ve yürüme kayıtlarında pencere başına $V$ değerini hesapla ve zaman içinde çiz.
2. Birinci ve ikinci özdeğeri 2B düzlemde çiz; DBSCAN ile kümele.
3. Yanlış alarm süzgecini ekle; ROC eğrisini süzgeçli ve süzgeçsiz karşılaştır.
4. Aynı pipeline'ı RSSI varyansıyla kur ve iki ROC eğrisini üst üste çiz.

## Kendini kontrol et

??? question "Durgun bir odada en büyük özdeğer neden pencere uzunluğuna yaklaşır?"
    Bütün paketler birbirine çok benzer; korelasyon matrisi neredeyse tamamen
    1'lerden oluşur. Böyle bir matrisin tek büyük özdeğeri $n$'dir.

??? question "Bu yöntem hareketsiz oturan birini neden kaçırır?"
    Öznitelik değişime bakar. Kişi hareket etmezse kanal yine durgundur.
    Varlık için ayrı bir yöntem gerekir (modül 12).
