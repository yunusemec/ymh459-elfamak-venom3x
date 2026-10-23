# LAB 3 · Threat & Risk + Risk Matrix — PaketPro Sürümü (Venom 3X'e uyarlanmış)

| Ad Soyad | Grup | Tarih |
|---|---|---|
| Yunus Emeç | 1.Şube / Gece-B |   |

**Çıktı:** Risk Register → Evidence Pack **EP 04 Cyber Risk Assessment**

**Şablon:** Safety 4.0 Bootcamp laboratuvar föyü, PaketPro 3000 Sürümü. "PaketPro'nun kapıları" ipucu kutusu Venom'un kapılarıyla değiştirildi; senaryo kalıbı ve puanlama aynıdır.

**Girdi:** LAB 1 safety function'ları (SF-01…SF-04) ve LAB 2 kapıları (K-01…K-06). Formül: **LAB 2'deki kapı × LAB 1'deki korunan fonksiyon = bir tehdit senaryosu.** **Kaynaklar:** [00-makine-kimlik-karti.md](../00-makine-kimlik-karti.md).

> **Kavram (föyden):** Senaryo beş parçadır: kim → hangi kapı → ne yapar → zincir → **FİZİKSEL** sonuç. Skor = L × S × E (her biri 1–3). Kural: **S=3 ise** skor düşük olsa bile senaryo öne alınır — insana zarar görünür kalır.
>
> **Senaryo kalıbı (föyden):** `[PROFİL]`, `[GİRİŞ]` üzerinden içeri girer ve `[EYLEM]` yapar; bu, `[ZİNCİR]` yoluyla `[EMNİYET FONKSİYONU]`'nu bozar ve sonuçta `[FİZİKSEL ETKİ]` oluşur.

> **Venom 3X'in kapıları (ipucu):** USB/program aktarımı (K-01) · uzak servis — varsayım (K-02) · kablosuz el çarkı — hareket + acil stop (K-03) · paylaşılan panel hesabı / parametre yetkisi (K-04) · fabrika/ofis ağı — varsayım (K-05) · emniyet konfigürasyonuna mühendislik erişimi (K-06).
>
> **Fiziksel sonuç adayları:** spindle/takımda el-kol kesilmesi, köprü/eksende ezilme, makaslı yükleme platformunda veya konveyörde el sıkışması, kırılan takımın veya tutuşunu kaybeden parçanın fırlaması.

## Ölçek göstergeleri (föy destesinden — her puan buna dayandırıldı)

- **L — kapı ne kadar kolay istismar edilir:** 1 Zor (güçlü kimlik doğrulama, güncel yazılım, bilinen açık yok; özel bilgi veya fiziksel erişim gerekir) · 2 Orta (kimlik bilgisi gerekir ama zayıf, paylaşılan ya da ele geçirilebilir) · 3 Kolay (kimlik doğrulama yok ya da varsayılan).
- **S — fiziksel sonuç ne kadar ağır** (LAB 1'deki Safety Function Map'ten): 1 Yaralanma yok · 2 Hafif, geri dönüşlü · 3 Ağır/kalıcı yaralanma, ölüm.
- **E — yol dışarıya ne kadar açık:** 1 Kapalı (yalnız makine başında, fiziksel erişimle) · 2 Sınırlı (fabrika/kurumsal ağdan ya da ara sıra açılan kontrollü dış bağlantı) · 3 Açık (internetten doğrudan ya da sürekli açık).

## Görev — senaryolar ve puanlama

Dört senaryo, **dört saldırgan profilinin dördü** (fırsatçı dış, meraklı içeriden, tedarik zinciri, hedefli) ve **altı kapının dördü** kullanıldı. Kapılar LAB 2 envanterinde kayıtlıdır.

### R-01 · Kablosuz el çarkından güvenli hareketin bozulması

> **Fırsatçı dış saldırgan**, **kablosuz el çarkı (K-03)** üzerinden içeri girer ve **makineyle eşleşip manuel moddaki hız sınırını aşan bir eksen komutu** yapar; bu, **el çarkının hareket ve acil stop sinyallerini taşıyan kablosuz bağlantının kontrol ünitesine doğrudan girmesi** yoluyla **SF-03 Manuel modda güvenli hareket**'i bozar ve sonuçta **ayar için tablaya uzanan operatörün eline köprü veya spindle çarpar: ezilme, kesilme** oluşur.

| Eksen | Puan | Ölçek göstergesine dayanan gerekçe |
|---|---|---|
| **L** | 2 | Eşleştirme bir kimlik bilgisidir ama protokolü ve güvenliği kamuya açık değil; "zayıf ya da ele geçirilebilir kimlik bilgisi" göstergesine uyuyor (**Varsayım**). |
| **S** | 3 | SF-03 bozulursa en kötü sonuç uzuv ezilmesi/kesilmesi: "ağır/kalıcı yaralanma". |
| **E** | 2 | Bağlantı kablosuz ama menzili fabrika içiyle sınırlı: "sınırlı" göstergesi. |
| **Skor** | **12** | **Yüksek** · S3 ⚑ |

*Not:* Aynı kapı **SF-01**'e de dokunur. El çarkındaki acil stop'un sinyali bu kablosuz bağlantıdan geçer [K13 s.10]; bağlantı bozulduğunda makine güvenli duruma geçmiyorsa acil durdurma da etkilenir. S yine 3'tür.

### R-02 · Emniyet konfigürasyonunun içeriden değiştirilmesi

> **Meraklı içeriden** (yetkisi olan ama sınırı aşan bir bakımcı), **emniyet konfigürasyonuna mühendislik erişimi (K-06)** üzerinden içeri girer ve **üretimi hızlandırmak için acil durdurmanın tepki/durdurma parametresini değiştirme** işini yapar; bu, **emniyet mantığından STO'ya giden durdurma zincirinin gecikmesi** yoluyla **SF-01 Acil durdurma**'yı bozar ve sonuçta **acil stop'a basıldığında spindle geç durur, operatörün eli kesilir**.

| Eksen | Puan | Gerekçe |
|---|---|---|
| **L** | 1 | Emniyet parametresini bilerek değiştirmek "özel bilgi ve fiziksel erişim" gerektirir: "zor" göstergesi. |
| **S** | 3 | SF-01 bozulursa en kötü sonuç ağır kesilme veya ölüm. |
| **E** | 1 | Emniyet konfigürasyonu Z3'te, yalnızca makine başından erişiliyor (LAB 2 C4): göstergedeki "pano içindeki programlama portu" durumu. |
| **Skor** | **3** | **Düşük** · S3 ⚑ |

### R-03 · Tedarik zincirinden gelen programla vakum tutuşunun kaybı

> **Tedarik zinciri saldırganı**, **USB/program aktarımı (K-01)** üzerinden, ele geçirilmiş bir CAM/nesting yazılım güncellemesiyle içeri girer ve **parçanın bulunduğu vakum bölgesini işleme sırasında kapatan, tabla koruma eşiğini de değiştiren bir program/parametre yükleme** işini yapar; bu, **vakum bölgelerinin yazılımdan, aktüatörle açılıp kapanması** yoluyla **SF-04 Vakum tutuşu kaybında durdurma**'yı (izleme aynı yazılımdaysa) bozar ve sonuçta **tutuşunu kaybeden parça veya kırılan takım fırlayıp operatörü yaralar**.

| Eksen | Puan | Gerekçe |
|---|---|---|
| **L** | 2 | Program yükleme için panelde kişi bazlı yetki kamuya açık değil (**Varsayım:** paylaşılan operatör hesabı): "zayıf/paylaşılan kimlik bilgisi" göstergesi. |
| **S** | 3 | SF-04 bozulursa en kötü sonuç, fırlayan parça veya takımla ağır yaralanma. |
| **E** | 2 | Program makine başından USB ile ya da fabrika ağındaki CAM bilgisayarından gelir: "fabrika/kurumsal ağ" göstergesi. |
| **Skor** | **12** | **Yüksek** · S3 ⚑ |

*Not:* Tabla Koruma (MF-01) bu senaryoda **güvence değildir**. Kendisi de aynı yazılımda bir parametre olduğu için, programla birlikte değiştirilebilir.

### R-04 · Uzak servis yolundan fidye (altın kural örneği)

> **Hedefli saldırgan**, **uzak servis bağlantısı (K-02, varsayım)** üzerinden içeri girer ve **kontrol PC'sini fidye yazılımıyla kilitleme** işini yapar; bu, **kontrol PC'sinin şifrelenmesi** yoluyla **hiçbir emniyet fonksiyonunu bozmaz** ve sonuçta **üretim durur, veri kaybolur — fiziksel etki yoktur**.

| Eksen | Puan | Gerekçe |
|---|---|---|
| **L** | 3 | Uzak servis varsayılan veya zayıf kimlikle sürekli açıksa "kolay" göstergesi (**Varsayım**). |
| **S** | 1 | Sonuç üretim ve veri kaybı: "yaralanma yok — emniyet bulgusu değil". |
| **E** | 3 | İnternetten doğrudan erişilen uzak yol: "açık" göstergesi. |
| **Skor** | **9** | **Yüksek** · emniyet bulgusu değil |

R-04 bilerek eklendi. Skoru (9), R-02'nin (3) üç katı. Ama zincir "üretim durdu / veri şifrelendi" ile bitiyor ve kalıbın `[EMNİYET FONKSİYONU]` ile `[FİZİKSEL ETKİ]` boşlukları dolmuyor. **Altın kural:** bu bir emniyet bulgusu değildir. Register'da işletme riski olarak kalır; emniyet önceliği S3 senaryolarındadır.

## Soru 1 — En yüksek öncelikli senaryonuz hangisi? Bir cümleyle: neden bu?

**R-01.** En yüksek skor (12) ve S=3'e sahip; üstelik aynı kapıdan iki emniyet fonksiyonuna birden dokunuyor (SF-03 ve el çarkındaki acil stop üzerinden SF-01). R-03 de 12 puan ve S=3. Eşitliği, R-01'in iki fonksiyona dokunması bozuyor.

## Soru 2 — S=3 olup skoru düşük kalan senaryonuz var mı? Nasıl görünür kılacaksınız?

**Evet: R-02 (skor 3, Düşük bant, S=3).** Matris onu listenin dibine gömüyor; ama sonunda bir insanın eli kesiliyor. Görünür kılmak için:
- Register'da **S3 bayrağı** konur ve R-02 ayrı bir **S3 yönetim listesine** alınır.
- Skoru 9 olan ama S=1 olan **R-04'ün önüne** konur; bütçe önce R-02'ye gider.
- Düşük skoru E=1'den, yani kapalı kapıdan geliyor. Bu, kapıyı kapalı tutmanın ne kadar kritik olduğunu da gösterir: E bir basamak artarsa skor ikiye katlanır.

> **Altın kural kontrolü:** R-01, R-02 ve R-03'ün zinciri fiziksel sonuçla (ezilme, kesilme, fırlama) bitiyor. R-04'ün zinciri ise üretim/veri ile bitiyor, dolayısıyla emniyet bulgusu değil.

## Çıktı — Risk Register (EP 04)

**Tarih:** 22.10.2026 · **Hazırlayan:** Yunus Emeç (1.Şube / Gece-B) · **Makine ve sürüm:** Elfamak Venom 3X, otomatik yükleme/boşaltmalı konfigürasyon (2128 / 2137 / 2142), Beckhoff kontrol; yazılım sürümleri kamuya açık değil.

**Sıralama:** skora göre; S3 bayrakları işaretli. **S3 yönetim listesi:** R-01, R-03, R-02.

| Sıra | Risk ID | Senaryo (profil → kapı → eylem → zincir → fiziksel sonuç) | Etkilenen SF (LAB 1) | Zone / conduit (LAB 2) | L | S | E | Skor | Bant | S3 | Mevcut önlem | Önerilen önlem (gereksinim) | Artık risk | Sahip (RACI "A") — öneri | Hedef | Kanıt → EP |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | **R-01** | Fırsatçı dış → el çarkı (K-03) → eşleşip hız sınırını aşan komut → kablosuz bağlantı → **ezilme/kesilme** | SF-03 (+SF-01) | Z2 · C3 | 2 | 3 | 2 | **12** | Yüksek | ⚑ | Kamuya açık kanıt yok | Eşleştirme, bağlantı kopunca dur, onay butonu, manuel hız sınırı, acil stop sinyali kaybında güvenli dur *(LAB 4 R5)* | Düşük | Elfamak Ar-Ge / elektronik sorumlusu (C: Elfatek) | 20.01.2027 | EP 06 |
| 2 | **R-03** | Tedarik zinciri → USB/program (K-01) → vakum bölgesini kapatan program + eşik değişikliği → yazılımla yönetilen vakum → **fırlayan parça/takım** | SF-04 (MF-01 dolaylı) | Z0→Z2 · C1 | 2 | 3 | 2 | **12** | Yüksek | ⚑ | Tabla Koruma (makine koruma; güvence değil) | Program bütünlük kontrolü ve yükleme kaydı; USB kısıtı; vakum izlemenin programla devre dışı bırakılamaması *(LAB 4 R1–R2)* | Orta | Elfamak yazılım / Ar-Ge sorumlusu | 20.01.2027 | EP 06, 09 |
| 3 | **R-04** | Hedefli → uzak servis (K-02) → fidye → PC şifrelenir → **üretim/veri kaybı** | — (emniyet bulgusu değil) | Dış→Z1→Z2 · C2 | 3 | 1 | 3 | **9** | Yüksek | — | Kamuya açık kanıt yok | Jump server, VPN, MFA, kişisel hesap, kayıt, varsayılan kapalı + yedekleme *(LAB 4)* | Orta | Elfamak servis sorumlusu | 20.01.2027 | EP 02 |
| ⚑ | **R-02** | Meraklı içeriden → emniyet konfigürasyonu (K-06) → durdurma parametresini değiştir → STO gecikir → **ağır kesilme** | SF-01 | Z2→Z3 · C4 | 1 | 3 | 1 | **3** | Düşük | ⚑ | Kamuya açık kanıt yok | Ayrı yetki, makine başı erişim, değişiklik kaydı, değişiklik sonrası safety validation *(LAB 4 R2–R4)* | Düşük | Elfamak elektrik-otomasyon sorumlusu | **21.11.2026** (S3 → öne alındı) | EP 03, 06 |

*Sahip önerileri, firmanın organizasyon şeması kamuya açık olmadığı için rol düzeyindedir. Hedef tarihler, föy destesindeki bant kararlarından alındı: Yüksek → 90 günlük planın ilk sıraları, S3 → öne alınır (30 gün). 22.10.2026'dan 90 gün sonrası, **20.01.2027**, Makine Tüzüğü 2023/1230'un uygulanmaya başladığı güne denk geliyor.*

**EP 04 durumu: Taslak.**

---

*Bu föyün çıktısı Risk Register → Evidence Pack EP 04 Risk Assessment başlığına oturur.*

*Not (LAB 3 kuralı): Şablonu kopyalamak serbest, gerekçeyi kopyalamak değil — L/S/E gerekçeleri Venom 3X'in kendi kapı ve fonksiyonlarına göre yazıldı.*

*Bu bir eğitim çıktısıdır, resmî denetim değildir.*
