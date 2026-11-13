# LAB 7 · AI Safety Challenge — Genel Sürüm, Venom 3X için

| Ad Soyad | Grup | Tarih |
|---|---|---|
| Yunus Emeç | 1.Şube / Gece-B | 13.11.2026 |

- **Çıktı:** AI Fail-Safe Decision → Evidence Pack **EP 03 + EP 15**
- **Şablon:** Safety 4.0 Bootcamp laboratuvar föyü, Genel Sürüm (Şişeleme Hattı). Sorular ve karar tablosu şablondaki gibidir; cevaplar Venom 3X içindir.
- **Önemli not:** Kamuya açık bilgiye göre Venom 3X'te bir yapay zekâ bileşeni **yok**. Cevaplar, makineye eklenmesi düşünülen varsayımsal bir YZ'li görsel kontrol için yazıldı. Ayrıntılı senaryo, mimari ve mevzuat: [lab7-paketpro-surumu.md](lab7-paketpro-surumu.md).

> **Kavram (föyden):** Prediction ≠ Safety: Yapay zekâ bir karar üretir; güvenliği garanti eden mimari YZ'nin dışında tanımlanmalıdır.
>
> **Araçlar:** fail-safe · human override · monitoring · confidence threshold · fallback.

**Akış (şablon → Venom):** Kamera → YZ modeli → OK / RED → Parametre → ~~Robot~~ **CNC (köprü + spindle)**

Venom'da "parametre", YZ'nin plaka yerleşimine göre önerdiği vakum bölge seçimidir. Yanlış bir OK, parçanın tutuşunu zayıflatıp fırlamasına yol açabilir (LAB 1 SF-04, LAB 3 R-03). Yani YZ hatası fiziksel sonuca gidebilir.

## Görev — üç başarısızlıkta güvenli davranış

**1. Model yanlış sınıflandırdı: Kusurlu parçaya OK verdi. Sistem ne yapmalı? İkinci kontrol / insan onayı var mı?**

YZ'nin "OK"i tek başına işlemeyi başlatmaz. **İkinci kontrol deterministiktir:**
- referanslama dayamalarının sensörü plakanın yerinde olduğunu doğrular,
- vakum basıncı eşiği aşılmadan işleme başlamaz (SF-04),
- YZ'nin ölçtüğü plaka boyutu CAM programındaki boyutla karşılaştırılır.

Biri tutmazsa makine işlemeye başlamaz. Her yeni programın ilk plakası **insan onayıyla** başlar. Kusurlu bir parçaya verilen OK ise bir kalite hatasıdır (S1). Kayıtlardan izlenir ve modelin yeniden eğitilmesine girdi olur.

**2. Girdi manipüle edildi: Kamera verisi bozuk/sahte. Nasıl fark edilir? Şüpheli girdide ne yapılır?**
- **Nasıl fark edilir:** donmuş ya da tekrar oynatılan görüntü için kare sayacı ve zaman damgası; ahşap tozu ya da kirlenmiş lens için netlik ve kontrast ölçümleri; sensörlerle tutarsızlık (görüntü "plaka var" derken dayama sensörü "yok" diyorsa).
- **Şüpheli girdide:** karar **RED** sayılır, otomatik çevrim durur ve operatör uyarılır. Makine YZ'siz çalışmaya geçer: vakum bölgeleri YZ'nin önerisine göre değil, CAM programına göre seçilir.

**3. Confidence düştü: Model "emin değilim" diyor. Eşik ne olmalı? Altında: dur / insana sor / fallback?**
- **Eşik nasıl belirlenir:** Tahminle değil, doğrulama verisiyle. Yanlış OK oranı kabul edilebilir sınırın altında kalacak şekilde seçilir. Fiziksel sonuca giden kararlar (plaka yerleşimi) için eşik, kalite kararlarından (parça kusuru) daha yüksek tutulur.
- **Eşiğin altında:** önce **dur** (yükleme bekletilir), sonra **insana sor** (operatör onayı). Onay gelmezse **fallback**: YZ'siz güvenli mod.
- Güven skorunun zaman içindeki düşüşü (toz, ışık değişimi) ayrıca **izlenir**.

## Karar tablosu — AI Fail-Safe Decision

| Başarısızlık | Tanımladığınız güvenli davranış | Kavram |
|---|---|---|
| Model yanlış sınıflandırdı | YZ'nin OK'i tek başına yetmez: dayama sensörü + vakum basıncı + CAM boyutu kontrolü; yeni programda insan onayı | fail-safe · human override |
| Girdi manipüle edildi | Girdi bütünlüğü kontrolü; şüpheli girdi = RED; YZ'siz güvenli moda geçiş | monitoring · fallback |
| Confidence düştü | Doğrulamayla belirlenmiş eşik; altında dur → insana sor → YZ'siz mod; güven eğilimi izlenir | confidence threshold · human override · fallback |

Hepsinin üstünde tek kural: **YZ, emniyet zincirinin (SF-01…SF-04) parçası değildir** ve hiçbir emniyet parametresine yazamaz.

---

*Bu föyün çıktısı AI Fail-Safe Decision → Evidence Pack EP 03 + EP 15 başlığına oturur.*

*Bu bir eğitim çıktısıdır, resmî denetim değildir.*
