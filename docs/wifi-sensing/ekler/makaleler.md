# Makaleler

Dersin dayandığı makaleler ve okuma sırası. PDF'ler sitede barındırılmaz;
her makale için yayıncı ya da arXiv bağlantısı verilir.

## Makale nasıl okunur

1. **Özet ve sonuç:** Problem ne, iddia ne, hangi sayıyla destekleniyor?
2. **Şekiller:** Her şekil neyi kanıtlamak için orada? Eksenleri oku.
3. **Kurulum:** Donanım, anten, bant genişliği, ölçüm hızı, oda, kişi sayısı.
4. **Yöntem:** Öznitelik → karar adımlarını kendi cümlelerinle bir akış olarak yaz.
5. **Değerlendirme:** Eğitim ve test nasıl bölünmüş? Başka odada test var mı?
6. **Sınırlar:** Yazarların söylemediği varsayımlar neler?
7. **Kart:** Aşağıdaki şablonla tek sayfalık özet çıkar ve modül sayfasına ekle.

**Kart şablonu:** Problem · Veri ve donanım · Öznitelik · Yöntem · Sonuç · Sınırlar · Yeniden üretim

## Temel makaleler (ilk okunacaklar)

Bu dört makale kısa, okunması kolay ve Intel 5300 dönemini temsil ediyor.
Hepsi yalnızca CSI genliğini kullanıyor.

### FIMD (2012) { #fimd }

J. Xiao, K. Wu, Y. Yi, L. Wang, L. M. Ni. *FIMD: Fine-grained Device-free Motion Detection.*
IEEE ICPADS 2012. <https://doi.org/10.1109/ICPADS.2012.40>
→ [11 · Hareket](../yontemler/hareket.md)

### Pilot (2013) { #pilot }

J. Xiao, K. Wu, Y. Yi, L. Wang, L. M. Ni. *Pilot: Passive Device-free Indoor
Localization Using Channel State Information.* IEEE ICDCS 2013.
<https://doi.org/10.1109/ICDCS.2013.49>
→ [12 · Varlık](../yontemler/varlik.md), [13 · Konumlama](../yontemler/konumlama.md)

### SVM ve CSI parmak izi (2017) { #svm-csi }

R. Zhou, X. Lu, P. Zhao, J. Chen. *Device-Free Presence Detection and Localization
With SVM and CSI Fingerprinting.* IEEE Sensors Journal, 2017.
<https://doi.org/10.1109/JSEN.2017.2762428>
→ [12 · Varlık](../yontemler/varlik.md), [13 · Konumlama](../yontemler/konumlama.md)

### LiFS (2016/2018) { #lifs }

J. Wang, J. Xiong, H. Jiang, K. Jamieson, X. Chen, D. Fang, C. Wang.
*Low Human-Effort, Device-Free Localization with Fine-Grained Subcarrier Information.*
IEEE TMC (konferans sürümü ACM MobiCom 2016).
<https://doi.org/10.1109/TMC.2018.2812746>
→ [5 · Doppler ve Fresnel](../temeller/doppler-fresnel.md), [13 · Konumlama](../yontemler/konumlama.md)

!!! warning "Okurken dikkat"
    - FIMD ve Pilot $h = |h|e^{j\sin\angle h}$ yazıyor; doğrusu $h = |h|e^{j\angle h}$.
    - FIMD'nin uzaklık formülünde kareler toplanacakken eksi var.
    - SVM makalesinde FP ve FN tanımları ters yazılmış.

## Okuma sırası (01–09) { #okuma-sirasi }

| # | Makale | Bağlantı | Modül |
|---|---|---|---|
| 01 | Exposing the CSI: A Systematic Investigation of CSI-based Wi-Fi Sensing Capabilities and Limitations | [arXiv 2302.00992](https://arxiv.org/abs/2302.00992) | [14](../yontemler/aktivite.md) |
| 02 | SHARP: Environment and Person Independent Activity Recognition with Commodity IEEE 802.11 Access Points | [arXiv 2103.09924](https://arxiv.org/abs/2103.09924) | [14](../yontemler/aktivite.md) |
| 03 | <span id="genelleme"></span>A Survey on Wi-Fi Sensing Generalizability | [arXiv 2503.08008](https://arxiv.org/abs/2503.08008) | [19](../yontemler/genelleme.md) |
| 04 | WiMANS: A Benchmark Dataset for WiFi-based Multi-user Activity Sensing | [arXiv 2402.09430](https://arxiv.org/abs/2402.09430) | [18](../yontemler/coklu-kisi.md) |
| 05 | MM-Fi: Multi-Modal Non-Intrusive 4D Human Dataset for Versatile Wireless Sensing | [arXiv 2305.10345](https://arxiv.org/abs/2305.10345) | [18](../yontemler/coklu-kisi.md) |
| 06 | Widar3.0: Zero-Effort Cross-Domain Gesture Recognition With Wi-Fi | [Proje sayfası](https://tns.thss.tsinghua.edu.cn/widar3.0/) | [16](../yontemler/jest-yuruyus.md) |
| 07 | GaitSense: Towards Ubiquitous Gait-Based Human Identification with Wi-Fi | [DOI](https://doi.org/10.1145/3466638) | [16](../yontemler/jest-yuruyus.md) |
| 08 | SiFall: Practical Online Fall Detection with RF Sensing | [arXiv 2301.03773](https://arxiv.org/abs/2301.03773) | [17](../yontemler/dusme.md) |
| 09 | WiFi-based Real-time Breathing and Heart Rate Monitoring during Sleep | [arXiv 1908.05108](https://arxiv.org/abs/1908.05108) | [15](../yontemler/solunum.md) |

## Ders kitabı ve listeler

- Hands-on Wireless Sensing (Tsinghua) web eğitimi: <https://tns.thss.tsinghua.edu.cn/wst/docs/intro/>
- Awesome WiFi CSI Sensing: <https://github.com/NTUMARS/Awesome-WiFi-CSI-Sensing>
- Awesome Wireless Sensing Generalization: <https://github.com/airslab2020/awesome-wireless-sensing-generalization>
