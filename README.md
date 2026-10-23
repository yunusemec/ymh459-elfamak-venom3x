# YMH459 · Safety 4.0 Analizi — Elfamak Venom 3X

**Ders:** Yazılım Mühendisliğinde Güncel Konular (YMH459, İÖ) · Fırat Üniversitesi Teknoloji Fakültesi Yazılım Mühendisliği

**Öğrenci:** Yunus Emeç (1.Şube / Gece-B) · **Dönem:** 2026 Güz

**Firma / Makine:** Elfamak Makina Teknolojileri Ltd. Şti. / Venom 3X CNC İşleme Merkezi (ahşap CNC router)

**Dernek:** AİMSAD (Ağaç İşleme Makine Sanayicileri)

**Proje panosu (Trello):** https://trello.com/b/yyuuVcIz/ymh459-elfamak-venom-3x-safety-40

Bu depo, ilk dört Safety 4.0 laboratuvar föyünün Venom 3X makinesine uygulanmış hâlini içerir: her lab için **Genel Sürüm** (Şişeleme Hattı şablonu) ve **PaketPro Sürümü** (makineye uyarlanmış şablon) olmak üzere **4 + 4 = 8 föy**. SWOT + SMART analizi son aşamada eklenecektir.

## Klasör yapısı

```
ymh459-elfamak-venom3x/
├── README.md
├── 00-makine-kimlik-karti.md            Venom 3X hakkında kamuya açık her şey, kaynaklı
├── lab1-safety-architecture/            Çıktı: Safety Function Map → EP 03
│   ├── lab1-genel-surum.md
│   └── lab1-paketpro-surumu.md
├── lab2-iec62443-mini-workshop/         Çıktı: Envanter + Zone/Conduit Diagram → EP 05
│   ├── lab2-genel-surum.md
│   └── lab2-paketpro-surumu.md
├── lab3-threat-risk-matrix/             Çıktı: Risk Register → EP 04
│   ├── lab3-genel-surum.md
│   └── lab3-paketpro-surumu.md
└── lab4-secure-remote-access/           Çıktı: Secure Architecture → EP 02 + EP 06
    ├── lab4-genel-surum.md
    └── lab4-paketpro-surumu.md
```

- **`labN-genel-surum.md`** — Genel Sürüm föyü (Şişeleme Hattı). Sorular şablondaki gibidir, cevaplar Venom 3X içindir.
- **`labN-paketpro-surumu.md`** — PaketPro 3000 Sürümü föyü. PaketPro'nun kendi makinesine yaptığı gibi föy Venom 3X'e uyarlanmıştır (bağlam kutusu, varlık listesi, kapılar, makineye özel sorular); tam çıktı tabloları buradadır.

İki sürüm aynı kodları kullanır: **SF-** emniyet fonksiyonu (LAB 1) · **V-** varlık, **K-** kapı, **Z** bölge, **C** geçiş (LAB 2) · **R-** risk (LAB 3) · **R1–R5** gereksinim (LAB 4).

## Okuma sırası

`00 → lab1 → lab2 → lab3 → lab4`. Her lab bir öncekinin çıktısını kullanır: LAB 3 senaryoları LAB 1 fonksiyonları ile LAB 2 kapılarından doğar; LAB 4 LAB 3'ün en yüksek skorlu senaryolarını tasarım gereksinimleriyle kırar.

## Yöntem ve sınırlar

- Analiz **yalnızca kamuya açık kaynaklara** dayanır: firma web sitesi, ürün sayfaları, Venom 3X kataloğu ve AT uygunluk beyanı. Firmayla iletişim kurulmamıştır.
- Her bilginin kaynağı `00-makine-kimlik-karti.md` içindeki `[K…]` listesine bağlıdır. Kaynakta olmayan bilgiler **"Varsayım"** olarak işaretlenmiştir.
- Analiz **savunma odaklıdır:** her zafiyet bir saldırı aracına değil, bir **gereksinime/öneriye** çevrilmiştir. Gerçek makineye yönelik bir exploit veya adım adım saldırı planı üretilmemiştir.
- Föy şablonları, INSPECCO × Kriptarium **Safety 4.0 Bootcamp** eğitim materyallerinden ders için uyarlanmıştır. Bu depo bir **eğitim çıktısıdır; resmî denetim, uygunluk değerlendirmesi veya belgelendirme değildir** ve CE/mevzuat uygunluğu garantisi vermez.
