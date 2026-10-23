# LAB 3 · Threat & Risk + Risk Matrix — Genel Sürüm, Venom 3X için

| Ad Soyad | Grup | Tarih |
|---|---|---|
| Yunus Emeç | 1.Şube / Gece-B |   |

**Çıktı:** Risk Register → Evidence Pack **EP 04 Cyber Risk Assessment**
**Şablon:** Safety 4.0 Bootcamp laboratuvar föyü, Genel Sürüm (Şişeleme Hattı). Sorular şablondaki gibidir; senaryolar Venom 3X içindir.
**Kodlar:** SF- (LAB 1), K- (LAB 2). Tam Risk Register (sahip, hedef, önlem, artık risk): [lab3-paketpro-surumu.md](lab3-paketpro-surumu.md).

> **Kavram (föyden):** Senaryo beş parçadır: kim → hangi kapı → ne yapar → zincir → **FİZİKSEL** sonuç. Skor = L × S × E (her biri 1–3). Kural: **S=3 ise** skor düşük olsa bile senaryo öne alınır.

## Görev — üç senaryo kurun ve puanlayın

**Senaryo cümleleri (kalıp: [PROFİL], [GİRİŞ] üzerinden içeri girer ve [EYLEM] yapar; bu, [ZİNCİR] yoluyla [EMNİYET FONKSİYONU]'nu bozar ve sonuçta [FİZİKSEL ETKİ] oluşur):**

- **R-01:** Fırsatçı dış saldırgan, kablosuz el çarkı (K-03) üzerinden içeri girer ve manuel moddaki hız sınırını aşan bir eksen komutu yapar; bu, kablosuz bağlantının kontrol ünitesine doğrudan girmesi yoluyla SF-03 Manuel modda güvenli hareket'i bozar ve sonuçta operatörün eline köprü veya spindle çarpar: ezilme, kesilme oluşur.
- **R-02:** Meraklı içeriden, emniyet konfigürasyonuna mühendislik erişimi (K-06) üzerinden içeri girer ve acil durdurmanın tepki parametresini değiştirir; bu, durdurma zincirinin gecikmesi yoluyla SF-01 Acil durdurma'yı bozar ve sonuçta spindle geç durur, operatörün eli kesilir.
- **R-03:** Tedarik zinciri saldırganı, USB/program aktarımı (K-01) üzerinden içeri girer ve parçanın vakum bölgesini kapatan bir program yükler; bu, vakum bölgelerinin yazılımla yönetilmesi yoluyla SF-04 Vakum tutuşu kaybında durdurma'yı bozar ve sonuçta tutuşunu kaybeden parça veya kırılan takım fırlayıp operatörü yaralar.

| Senaryo (kim→kapı→zincir→fiziksel sonuç) | L | S | E | Skor | Öncelik |
|---|---|---|---|---|---|
| R-01 · Fırsatçı dış → el çarkı → SF-03 → ezilme/kesilme | 2 | 3 | 2 | **12** | 1 · Yüksek · S3 |
| R-03 · Tedarik zinciri → USB/program → SF-04 → fırlama | 2 | 3 | 2 | **12** | 2 · Yüksek · S3 |
| R-02 · Meraklı içeriden → emniyet konfigürasyonu → SF-01 → kesilme | 1 | 3 | 1 | **3** | Düşük ama **S3 → öne alındı** |

Kritik 18–27 · Yüksek 9–17 · Orta 4–8 · Düşük 1–3

**Puan gerekçeleri (her puan ölçek göstergesine dayalı):**
- **L:** K-03 ve K-01 için 2, çünkü eşleştirme/panel hesabı kimlik bilgisi var ama zayıf ya da paylaşılan sayılıyor (**Varsayım**). K-06 için 1, çünkü emniyet parametresini değiştirmek özel bilgi ve fiziksel erişim ister.
- **S:** üçünde de 3, çünkü bozulan SF'lerin (SF-01, SF-03, SF-04) en kötü sonucu ağır/kalıcı yaralanma. Aynı fonksiyon her senaryoda aynı S'yi alır.
- **E:** K-03 için 2 (kablosuz ama fabrika içi menzil), K-01 için 2 (makine başı USB veya fabrika ağı), K-06 için 1 (yalnız makine başı).

**1. En yüksek öncelikli senaryonuz hangisi? Bir cümleyle: neden bu?**
R-01: en yüksek skor (12) ve S=3'e sahip, üstelik aynı kapıdan hem SF-03'e hem de el çarkındaki acil stop üzerinden SF-01'e dokunuyor.

**2. S=3 olup skoru düşük kalan senaryonuz var mı? Nasıl görünür kılacaksınız?**
Evet, R-02 (skor 3, S=3). Görünür kılmak için S3 bayrağı konur ve R-02 ayrı bir S3 yönetim listesine alınır. Skoru 9 olan ama S=1 olan fidye senaryosunun (R-04) da önüne geçirilir. Düşük skoru kapalı kapıdan (E=1) geliyor; bu yüzden kapıyı kapalı tutmak da önlemin bir parçasıdır.

> **Altın kural:** Zincir "veri çalındı / üretim durdu" ile bitiyorsa emniyet bulgusu değildir. Uzak servis fidyesi (R-04, skor 9, S=1) bu yüzden işletme riski olarak ayrı tutuldu.

---

*Bu föyün çıktısı Risk Register → Evidence Pack EP 04 Risk Assessment başlığına oturur.*
*Bu bir eğitim çıktısıdır, resmî denetim değildir.*
