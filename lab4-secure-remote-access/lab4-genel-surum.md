# LAB 4 · Secure Remote Access — Genel Sürüm, Venom 3X için

| Ad Soyad | Grup | Tarih |
|---|---|---|
| Yunus Emeç | 1.Şube / Gece-B |   |

**Çıktı:** Secure Architecture → Evidence Pack **EP 02 + EP 06**

**Şablon:** Safety 4.0 Bootcamp laboratuvar föyü, Genel Sürüm (Şişeleme Hattı). Sorular şablondaki gibidir; cevaplar Venom 3X içindir.

**Ayrıntılı mimari ve gereksinimler:** [lab4-paketpro-surumu.md](lab4-paketpro-surumu.md).

> **Kavram (föyden):** İki katman, ikisi de şart: erişim güvenliği + emniyet bağımsızlığı (girse bile insan korunur).

## Görev A — mevcut → hedef

| MEVCUT (çizin/yazın) | HEDEF (beş ilkeyle yeniden tasarlayın) |
|---|---|
| Uzak servis belirsiz; panel hesabı paylaşımlı sayılıyor; el çarkı (üzerinde acil stop) ve USB doğrudan kontrol ünitesinde; emniyet devresinin yapısı bilinmiyor | 1. Ara nokta (jump server) · 2. Kişisel hesap · 3. MFA · 4. Varsayılan kapalı, süre sınırlı · 5. Oturum kaydı |

Beş ilke LAB 2 Görev B'nin mimariye dökülmüş hâlidir; LAB 3 R-04'ün L ve E puanını düşürür.

## Görev B — functional safety köprüsü

**1. Saldırgan tüm önlemlere rağmen içeri girerse: emniyet fonksiyonu etkilenir mi? Neden?**

Emniyet mantığı kontrol ünitesinden ayrı (röle/Safety PLC, kendi STO'suyla) ise etkilenmez: saldırgan üretimi bozar, emniyeti bozamaz. Aynı sistemdeki bir modül ise etkilenebilir (LAB 3 R-02). Venom için bu ayrım kamuya açık değil; bu yüzden emniyet bağımsızlığı doğrulanması gereken bir gereksinimdir.

**2. Emniyet fonksiyonunun kontrol sisteminden bağımsız çalışması için GEREKSİNİMİ yazın (çözümü değil).**
- **R1.** SF-01, SF-02 ve SF-04, kontrol PC'si ele geçse bile çalışmaya devam etmeli; kontrol PC'sinden gelen komuta bağlı olmamalı.
- **R2.** Emniyet parametreleri hiçbir uzak yoldan/USB'den değişmemeli; yalnız makine başı + ayrı yetki + kayıt.
- **R3.** Kontrol → emniyet bağı yalnızca durum okuma yönünde.
- **R4.** Her emniyet parametresi değişikliğinden sonra safety validation + kayıt.
- **R5.** Kablosuz el çarkındaki acil stop, bağlantı kesilir veya sinyal doğrulanamazsa makineyi güvenli duruma geçirmeli (fail-safe).

**Tarafsızlık notu:** Bu föy çözüm tasarlatmaz; gereksinimi tanımlatır. Tasarım kararı firmanındır.

---

*Bu föyün çıktısı Secure Architecture → Evidence Pack EP 02 + EP 06 başlığına oturur.*

*Bu bir eğitim çıktısıdır, resmî denetim değildir.*
