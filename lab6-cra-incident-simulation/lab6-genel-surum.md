# LAB 6 · CRA Incident Simulation — Genel Sürüm, Venom 3X için

| Ad Soyad | Grup | Tarih |
|---|---|---|
| Yunus Emeç | 1.Şube / Gece-B | 06.11.2026 |

- **Çıktı:** Incident Workflow → Evidence Pack **EP 13 Incident Response**
- **Şablon:** Safety 4.0 Bootcamp laboratuvar föyü, Genel Sürüm (Şişeleme Hattı). Senaryo ve sorular şablondaki gibidir; cevaplar Venom 3X içindir.
- **Kodlar:** SF- (LAB 1), K- (LAB 2), R- (LAB 3), R1–R5 (LAB 4). Ayrıntılı akış, RACI ve CRA kaynakları: [lab6-paketpro-surumu.md](lab6-paketpro-surumu.md).

> **Senaryo (föyden):** Saat 10:15. Servis hesabında yetkisiz erişim tespit edildi. PLC konfigürasyonu değişmiş olabilir. Makine hâlâ çalışıyor. Vardiya sorumlusu sizsiniz.

> **Kavram (föyden):** Bir olayda en değerli iki şey zaman ve kanıttır. CRA'nın 24s / 72s / 14 gün yükümlülükleri, iyi bir müdahale akışının doğal kilometre taşlarıdır — ezber değil.

## Görev — zaman çizgisini doldurun

**1. 10:15 — ilk 15 dk: Kimi ararsınız? İlk üç eyleminiz?**

**Aranacaklar:**
- Bakım/OT sorumlusu: makineyi güvenli durduracak kişi.
- Elfamak servisi: hesabın sahibi ve CRA kapsamında bildirim yükümlüsü olan üretici.
- İşletmenin BT sorumlusu ve yönetim.

**İlk üç eylem:**
1. Kimse tehlike bölgesine girmeden, makineyi kontrollü bir duruşla durdurup enerjisini kesmek. Emniyet konfigürasyonu değişmiş olabilir; acil durdurmanın her zamanki gibi çalışacağı varsayılamaz.
2. Uzak erişim yolunu fiziksel olarak kesmek (ağ bağlantısı). Kontrol PC'si **resetlenmez, kapatılmaz**.
3. Olay günlüğünü başlatmak: saat, kim fark etti, ekranda ne görüldü, fotoğraflar.

**2. İlk 2 saat: Emniyet güvende mi? Neyi korursunuz (kanıt!)? Hangi hesap kapatılır?**

- **Emniyet:** Doğrulanana kadar güvende **sayılmaz**; makine üretime alınmaz. Doğrulama iki adımlı:
  - emniyet konfigürasyonunun sağlama değeri (checksum), bilinen iyi değerle karşılaştırılır;
  - yetkili bir kişi SF-01…SF-04 fonksiyon testlerini yapar.
- **Korunacak kanıt:** uzak erişim ve giriş kayıtları, kontrol PC'sinin olay günlükleri, CNC program ve parametre dosyalarının o anki kopyası, emniyet konfigürasyonunun kopyası.
- **Kapatılacak hesap:** ele geçirilen servis hesabı **devre dışı bırakılır, silinmez** (silmek de kanıtı yok eder). Aynı parolayı paylaşan başka hesaplar varsa onların da parolası değiştirilir.

**3. 24 saat — CRA erken uyarı: Hangi bilgi hazır olmalı?**

Erken uyarıyı ENISA'nın tek raporlama platformu üzerinden üretici (Elfamak) verir. Hazır olması gerekenler:
- olayın fark edildiği an,
- etkilenen ürün (Venom 3X, model, seri no, yazılım sürümü),
- olayın kötü niyetli bir eylemden kaynaklandığına dair şüphe olup olmadığı,
- aynı servis hesabını kullanan başka müşteri makinelerinin etkilenip etkilenmeyeceği.

**4. 72 saat — CRA bildirim: Kök neden, etki, önlem — kim ne yapıyor?**

| Kim | Ne yapıyor |
|---|---|
| Elfamak (üretici) | Bildirimi verir; kök nedeni araştırır (parola nasıl ele geçti?); diğer müşterileri değerlendirir |
| İşletme (OT + IT, RACI "R") | Kanıtı sağlar; makineyi temiz yedekten geri yükler |
| Safety | Emniyet doğrulamasını yapar |
| Yönetim (RACI "A") | Üretime dönüş kararını verir |

**5. 14 gün — son rapor: Hangi loglar/kayıtlar korunmuş olmalı?**
- Uzak erişim, jump server ve VPN kayıtları; kimlik doğrulama (MFA) kayıtları.
- Kontrol PC'sinin olay günlükleri.
- Program ve parametre değişiklik geçmişi ile dosyaların hash'leri; emniyet konfigürasyonunun öncesi ve sonrası sağlama değerleri.
- Ağ ve güvenlik duvarı kayıtları.
- Olay günlüğü, safety validation kaydı ve düzeltici önlem kaydı.

**Not:** Föyün "14 günü", aktif istismar edilen bir **zafiyetin** son raporudur; düzeltme yayımlandıktan sonra 14 gün içinde verilir. Bir **ciddi olayın** son raporu ise 72 saatlik bildirimden sonra **1 ay** içinde verilir. Ayrıntı ve kaynak PaketPro sürümünde.

> **En sık hata (föyden):** "Resetleyip devam edelim" — o düğme, kanıtı sonsuza dek siler. Önce emniyet, hemen sonra kanıt.

---

*Bu föyün çıktısı Incident Workflow → Evidence Pack EP 13 Incident Response başlığına oturur.*

*Bu bir eğitim çıktısıdır, resmî denetim değildir.*
