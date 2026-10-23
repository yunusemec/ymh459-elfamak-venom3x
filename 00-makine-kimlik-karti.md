# 00 · Makine Kimlik Kartı — Elfamak Venom 3X

> **YMH459 Yazılım Mühendisliğinde Güncel Konular** · Safety 4.0 analizi
>
> Ad Soyad: Yunus Emeç · Grup: 1.Şube / Gece-B · Tarih: 22.10.2026
>
> Bu belge yalnızca kamuya açık kaynaklara dayanır; firmayla iletişim kurulmamıştır.
>
> Her bilginin kaynağı köşeli parantezde verilmiştir ([K1] …). Kaynakta olmayan bilgi **Varsayım** olarak işaretlenmiştir.
>
> Bu bir eğitim çıktısıdır; resmî denetim, uygunluk değerlendirmesi veya belgelendirme değildir.

---

## 1. Firma

| Alan | Bilgi | Kaynak |
|---|---|---|
| Unvan | Elfamak Makina Teknolojileri ve Elektronik San. ve Tic. Ltd. Şti. | [K3], [K5] |
| Kuruluş | 2012, Elfa Grup şirketleri bünyesinde | [K5], [K6], [K13 s.3] |
| Konum | Karatay / Konya | [K4], [K5] |
| Çalışan sayısı | 25–49 | [K5] |
| Ürün gamı | Ahşap ve model/kalıp CNC router, CNC delik grubu, kapı grubu, soğuk pres, kasa sıkma | [K5], [K9], [K13 s.3] |
| Üretim beyanı | Firma, makinelerinin elektronik ve mekanik parçalarını kendi bünyesinde ürettiğini belirtiyor. Venom'da kontrol ve servo bileşenleri Beckhoff (veya Siemens) markalı; kablosuz el çarkının üzerinde ise grup şirketi Elfatek'in adı var (bkz. §4). | [K5], [K1], [K13 s.10, s.12] |
| İhracat | 10 ülkeye ihracat yaptığı haberi var; katalogun son sayfasındaki "Dünyaya ihraç ediyoruz" haritasında Avrupa'da çok sayıda işaret var (grup düzeyinde, ülke listesi yok) | [K7], [K13 s.14] |
| Dernek | AİMSAD üyesi (AİMSAD üye portalında listeli) | [K8] |
| Yayımlanmış politikalar | İSG, çevre ve kalite politikaları; KVKK metinleri | [K4] |
| Grup şirketleri | Endüstriyel elektronik (elfatek), plastik enjeksiyon ve kalıp (elfaKALIP), medikal elektronik (elfaMed), 3D yazıcı (Coraxis), savunma sanayi ürün ve yazılımları (Sasantek), ithalat-ihracat (elfaEXPORT) | [K13 s.2] |
| BT / siber güvenlik birimi | Kamuya açık bilgi yok. **Varsayım:** Elfamak'ın kendi bünyesinde ayrı bir BT veya siber güvenlik birimi yok. Dikkat: grup içinde elektronik ve yazılım alanında çalışan şirketler var; bu varsayım SWOT'ta açıkça tartışılacak. | [K13 s.2] |

## 2. Makine

| Alan | Bilgi | Kaynak |
|---|---|---|
| Ad | Venom 3X. Sitede ürün sayfası "VENOM LINE", belge sayfası "Venom 3X Belgeleri" adıyla geçiyor; ürün görselinin dosya adı (`k_VENOM.3X`) ikisini eşliyor. Çok hatlı bir varyantı da var: "VENOM MULTI LINE". | [K1], [K4], [K10] |
| Modeller | 1532, 2128, 2137, 2142, 2162 | [K13 s.5, s.12] |
| Çalışma alanı | X × Y × Z; ör. 2128: 2100 × 2800 × 250 mm, 2162: 2100 × 6200 × 250 mm | [K13 s.12] |
| Boyut / ağırlık | Makine 4,2–5,6 m, 4100–5350 kg; konveyör ve makaslı yükleme platformuyla birlikte hat 11,9–13,3 m, 6350–7600 kg (2128–2142) | [K13 s.11] |
| Kurulu güç | 25 kW (1532), 30 kW (diğerleri) | [K13 s.12] |
| Tip | Ahşap CNC router (bilgisayar kontrollü freze makinesi) | [K1], [K9] |
| Gövde | Çift kolonlu (double column) köprü; ray ve kremayer yataklar | [K13 s.6] |
| Eksen sayısı | 3 doğrusal eksen: çalışma alanı X × Y × Z olarak veriliyor; Z kursu 250 mm | [K13 s.12] |
| Konumlandırma | Seri üretim hatlarına yönelik; tam otomatik üretim hattı olarak tanıtılıyor | [K1], [K13 s.4] |
| Programlama | Parça CAD'de tasarlanır, CAM'de takım yolu oluşturulur, makine bu programla işler; elle programlama ve manuel çalışma da mümkün | [K9] |
| Kullanım kılavuzu | Sitede yayımlanmamış (Venom 3X belge sayfasında yalnızca katalog ve marka tescili var) | [K4] |

## 3. Hareketli ve enerjili kısımlar (→ LAB 1)

| Unsur | Kaynaktaki bilgi | Kaynak |
|---|---|---|
| Spindle (iş mili) ve kesici takım | HSK F63 takım tutucu, İtalyan menşeli spindle; 7,5–11 kW, 3000–24000 dev/dk | [K13 s.7, s.12] |
| Servo eksenler | Tüm hareket eksenlerinde Beckhoff servo motor ve servo sürücü | [K1], [K13 s.7] |
| Takım magazini | Köprü altı sabit magazin: 1532'de 10, diğer modellerde 15 takım; otomatik modda takım değişimi makine tarafından yapılıyor; gerekirse operatör kontrolünde manuel takım değişimi de mümkün | [K13 s.6, s.12] |
| Otomatik takım boyu ölçümü | Sistem takım boyunu ölçüp hafızaya kaydediyor ve işlemeye bu değerle devam ediyor | [K13 s.6] |
| Vakumlu tabla | Alüminyum; modele göre 4–12 vakum bölgesi; aktüatörlü bölge kontrolü; ikinci vakum pompası spindle'ın bulunduğu bölgeyi otomatik açıyor; Alman menşeli kuru tip vakum pompası (250–500 m³) | [K1], [K13 s.8, s.12] |
| Vakum bölge paneli | Bölgeler döner seçici şalterlerle açılıp kapanıyor; panelde ayrıca güç açma/kapama butonları var | [K13 s.8] |
| Otomatik yükleme sistemi | **Makaslı kaldırma platformu** (1600 kg) üzerinden; kesim bitince plakayı boşaltma konveyörüne aktarıyor, tablayı süpürüyor, ardından yeni plakayı tablaya yerleştiriyor. 2128, 2137, 2142'de standart; 1532 ve 2162'de yok | [K1], [K13 s.9, s.11, s.13] |
| Otomatik boşaltma konveyörü | Makinenin önünde (4150 × 2500 mm); sensörlü, öndeki parçalar alındıkça ilerliyor; süpürme sistemiyle birlikte çalışıyor. 2128, 2137, 2142'de standart | [K1], [K13 s.9, s.11, s.13] |
| Kablosuz el çarkı | Tüm modellerde standart. Fotoğrafta: üzerinde **kırmızı mantar başlı (acil durdurma görünümlü) buton**, çevirmeli el çarkı, eksen seçici ve butonlar; çarkın üzerinde "ELFATEK" yazıyor | [K1], [K13 s.10, s.13] |
| Referanslama sistemi | Bariyerli ve pistonlu (plakayı tablada konumlayan pnömatik dayamalar) | [K13 s.10, s.13] |
| Opsiyonlar | Çoklu delik ünitesi, agregat, vakum fincan bloğu | [K13 s.10, s.13] |
| Merkezi yağlama | Otomatik, zaman ve dozaj ayarlı merkezi yağlama sistemi | [K13 s.6] |

**Tabla Koruma Sistemi (yazılım):** Program hatalı olsa bile spindle'ın tablaya 1 mm kala kendini otomatik durdurduğu belirtiliyor; amaç tablanın, takımın ve spindle motorunun zarar görmemesi. Metin Venom'u adıyla anıyor. [K2], [K13 s.7]

→ *LAB 1'de değerlendirildi: emniyet fonksiyonu değil, makine koruma fonksiyonu.*

## 4. Kontrol ve dijital bileşenler (→ LAB 2 envanteri, altı kategori)

| Kategori | Kaynakta olan | Kamuya açık bilgide olmayan |
|---|---|---|
| Donanım | CNC kontrol: teknik tabloda "Beckhoff / Siemens" (seçeneğe bağlı) [K13 s.12]; ürün sayfası Beckhoff kontrol ünitesi, servo motor, sürücü ve kablo grubunu anlatıyor [K1] — **bu analiz Beckhoff konfigürasyonunu esas alır**; kontrol paneli (ekran + buton paneli) [K13 s.7]; vakum bölge paneli [K13 s.8]; Elfatek markalı kablosuz el çarkı [K13 s.10]; konveyör sensörleri [K1]; takım boyu ölçme probu [K13 s.10]; vakum pompaları ve bölge aktüatörleri [K1]; makaslı yükleme platformu [K13 s.9] | Ağ anahtarı, Safety PLC / emniyet rölesi, STO, spindle sürücüsü |
| Yazılım / firmware | Tabla Koruma yazılımı [K2]; takım boyu hafızası [K13 s.6]. Beckhoff genel olarak PC tabanlı kontrol teknolojisi geliştiriyor [K11]. Panel fotoğrafında ekranda pencereli bir masaüstü yazılımı görünüyor [K13 s.7, görsel gözlem]. Katalog "2D & 3D CAM ve Nesting çözümleri" sunuyor ve bir CAM yazılımı ekran görüntüsü gösteriyor [K13 s.10]; sitenin anahtar kelimelerinde bir CAM yazılımı adı (alphacam) geçiyor [K4]. | Kontrol yazılımının adı ve sürümü, işletim sistemi, sürücü firmware'leri, kullanılan CAM yazılımı. **Varsayım:** kontrol ünitesi PC tabanlı |
| Hesaplar | — | Operatör, bakım, servis ve tedarikçi hesapları; parola uygulamaları |
| Sertifika / anahtar | — | VPN, uzak erişim ve entegrasyon anahtarları; el çarkı eşleştirme bilgisi |
| Dış bağlantı | Kablosuz el çarkı; bağlantı türü belirtilmemiş [K1] | Program aktarım yolu (USB / ağ), uzak servis erişimi, fabrika ağı, MES/ERP, bulut |
| Kritik veri akışı | CAD/CAM → takım yolu programı → makine [K9]; takım boyu ölçümü → hafıza → işleme [K13 s.6]; tabla koruma eşiği (1 mm) [K2]; vakum bölge seçimi ve konveyör sensör sinyali [K1] | Bu akışların hangi kanaldan geçtiği; kimin değiştirebildiği |

**Belirsiz ifade:** Ürün sayfası ve katalog, Beckhoff bileşenleri arasındaki haberleşmeyi "yüksek güvenlikli haberleşme protokolü" olarak tanımlıyor [K1], [K13 s.7]. Protokolün adı ve "güvenlik" sözcüğüyle emniyetin (safety) mi güvenliğin (security) mi kastedildiği belirtilmemiş. → LAB 1–2'de bulgu olarak kullanıldı.

## 5. Emniyet donanımı (→ LAB 1)

- **Acil durdurma butonları:** Katalogdaki kontrol paneli fotoğrafında sarı zemin üzerinde kırmızı mantar başlı bir buton görünüyor [K13 s.7]. Kablosuz el çarkının üzerinde de aynı görünümde bir buton var [K13 s.10]. *(görsel gözlem)*
- **Önemli bulgu:** el çarkı kablosuz olduğundan, oradaki acil durdurmanın sinyali **radyo bağlantısı üzerinden** taşınıyor olmalı. Bu, emniyet sinyalinin bir dijital bağlantıya bağımlı olduğu anlamına gelir (LAB 1–4'te işlendi).
- **Erişim algılama / koruyucu:** Ürün sayfasında, AT beyanında, katalog render'larında (s.4–5) ve **teknik özellik tablolarında (s.12–13)** çit, ışık perdesi/bariyeri veya tampon yer almıyor; tablolar referanslama, el çarkı, yükleme, vakum gibi donanımları tek tek sayarken emniyet donanımına hiç satır ayırmıyor. Bu, makinede bulunmadığını kanıtlamaz. → "kamuya açık kanıt yok".
- AT beyanı EN 60204-1'e atıf yapıyor [K3]. Bu standart makinelerin elektrik donanımını kapsar; acil durdurmayı ve durdurma kategorilerini (0/1/2) tanımlar.
- **Varsayım:** acil durdurma devresinin yapısı (kablolu emniyet rölesi mi, programlanabilir emniyet modülü / Safety PLC mi), STO kullanımı ve durdurma kategorisi bilinmiyor.
- PLr / SIL değeri: kamuya açık bilgi yok.

## 6. Uygunluk ve mevzuat

| Alan | Bilgi | Kaynak |
|---|---|---|
| Belge | AT Uygunluk Beyanı, Konya, 13.01.2017; makine adı "CNC Router Makinası" | [K3] |
| Direktifler | 2006/42/AT Makine Emniyeti, 2014/35 Düşük Gerilim | [K3] |
| Standartlar | EN 60204-1, EN ISO 12100 | [K3] |
| Model / seri no | Ticari marka, model, üretim yılı ve seri no alanları boş; genel bir şablon | [K3] |

**Gözlemler.** Bunlar yargı değil, kamuya açık kanıtın durumudur.
1. ISO 13849 veya IEC 62061'e atıf yok → "kamuya açık kanıt yok". Bu, uygulanmadıkları anlamına gelmez.
2. Beyandaki adres (No: 5/A), sitedeki güncel adresten (No: 30/AD) farklı → beyan güncel bilgilerle yenilenmemiş görünüyor. [K3], [K4]
3. Beyan Düşük Gerilim Direktifini "2014/35/EC" ve "2014/35/AT" diye yazıyor; resmî kısaltması 2014/35/AB'dir (EU). Biçimsel bir not.
4. Makine Tüzüğü (AB) 2023/1230, 20 Ocak 2027'de geçiş dönemi olmadan uygulanmaya başlıyor ve siber güvenliği CE'nin ön şartı yapıyor [D1]. 2006/42/AT'ye dayanan bu beyanın, o tarihten sonra piyasaya arz edilecek makineler için 2023/1230'a göre yenilenmesi gerekecek.
5. CE beyanı, makinenin AB pazarına arzı için hazırlandığını gösteriyor. Dijital unsurlu bir ürün olarak CRA kapsamında olması muhtemel; CRA'nın bildirim yükümlülükleri 11 Eylül 2026'da başladı [D1]. Katalogun ihracat haritası Avrupa'yı yoğun gösteriyor [K13 s.14]. **Varsayım:** makine AB pazarına arz ediliyor; ihracat ülkeleri doğrulanmadı.

## 7. Bilinmeyenler (föylerde "Varsayım" olarak işaretlendi)

- Kontrol yazılımı, işletim sistemi, sürümler; kullanıcı hesapları
- Program aktarım yolu (USB / ağ)
- Uzak servis erişimi olup olmadığı ve nasıl yapıldığı
- Fabrika ağına, MES/ERP'ye veya buluta bağlantı
- Erişim algılama donanımı; emniyet devresinin yapısı (Safety PLC / röle), STO; PLr / SIL
- Kablosuz el çarkının bağlantı türü; bağlantı koparsa makinenin durup durmadığı; onay (enabling) butonu olup olmadığı
- Takım boyu verisini ve tabla koruma eşiğini kimin değiştirebildiği

## 8. Görsel inceleme (Venom 3X kataloğu)

Katalog PDF'i [K13] tarayıcıda açılıp **14 sayfanın tamamı** incelendi.

| Sayfa | Görülen | Kullanıldığı yer |
|---|---|---|
| s.2 | Elfa Grup şirketleri | §1 |
| s.3 | Firma tanıtımı; ürün grupları (CNC, kapı, model, delik) | §1 |
| s.4–5 | Makine çizimi ve render'ı; modeller; arka yükleme masası, ön boşaltma bandı, köprü; çit / ışık perdesi / tampon görünmüyor | §2, §5 |
| s.6 | Ray-kremayer, merkezi yağlama, takım magazini, otomatik takım boyu ölçümü | §3, §4 |
| s.7 | Spindle, Tabla Koruma, Beckhoff kontrol paneli: ekran + buton paneli, **acil durdurma görünümlü buton** | §3, §4, §5 |
| s.8 | Vakum bölge paneli (döner seçiciler), kuru tip vakum pompası, otomatik boşaltma ve süpürme | §3, §4 |
| s.9 | Boşaltma konveyörü; **makaslı** otomatik yükleme platformu | §3 |
| s.10 | **Kablosuz el çarkı (Elfatek, üzerinde acil durdurma görünümlü buton)**, boy ölçme probu, CAM/nesting yazılımı, bariyerli referanslama, kablo kanalı, opsiyonlar | §3, §4, §5 |
| s.11 | Boyut ve ağırlık tabloları (makine, konveyör, makas, hat) | §2 |
| s.12 | Teknik tablo: çalışma alanı, spindle, CNC kontrol (Beckhoff / Siemens), vakum, pano, magazin, güç | §2, §3, §4 |
| s.13 | Donanım tablosu: standart / opsiyonel; **emniyet donanımı satırı yok** | §3, §5 |
| s.14 | "Dünyaya ihraç ediyoruz" haritası | §1, §6 |

---

## Kaynaklar (erişim: 22.10.2026)

- **[K1]** Elfamak, VENOM LINE ürün sayfası — https://www.elfamak.com.tr/u_venom-line_17_tr.html
- **[K2]** Elfamak, ALTOR PLUS ürün sayfası (Tabla Koruma metni Venom'u da anıyor) — https://www.elfamak.com.tr/u_altor-plus_41_tr.html
- **[K3]** Elfamak, AT Uygunluk Beyanı (13.01.2017) — https://www.elfamak.com.tr/upload/pdf_CE.BELGESI_1572528817.pdf
- **[K4]** Elfamak, Dökümanlar ve Venom 3X Belgeleri sayfaları — https://www.elfamak.com.tr/dokumanlar_tr.html · https://www.elfamak.com.tr/dokuman_venom-3x-belgeleri_6_tr.html
- **[K5]** kariyer.net, Elfamak firma profili — https://www.kariyer.net/firma-profil/elfamak-makina-teknolojileri-ve-elektronik-san-tic-34142-242875
- **[K6]** DirectIndustry, Elfa Group şirket sayfası — https://www.directindustry.com/soc/elfa-group-40567.html
- **[K7]** Mynet Finans, "Konya'dan 10 ülkeye ahşap işleme makinesi ihracatı" — https://finans.mynet.com/haber/detay/finans/konyadan-10-ulkeye-ahsap-isleme-makinesi-ihracati/168699/
- **[K8]** AİMSAD üye portalı — https://twm.com.tr/tr/magazalar (üyelik 19.10.2026'da kontrol edildi)
- **[K9]** Elfamak, Ürünler sayfası (CNC router tanımı) — https://elfamak.com.tr/urunler_tr.html
- **[K10]** Elfamak, VENOM MULTI LINE ürün sayfası — https://www.elfamak.com.tr/u_venom-multi-line_52_tr.html
- **[K11]** Siskon, "Beckhoff Ürünlere Genel Bakış" — https://www.siskon.com.tr/dosya/PDF/Beckhoff.pdf
- **[K13]** Elfamak, Venom 3X kataloğu (14 sayfa, tamamı incelendi) — https://www.elfamak.com.tr/upload/pdf_VENOM.3X.KATALOG_1653640642.pdf
- **[D1]** Ders materyali: Safety 4.0 Bootcamp sunumu, "Neden şimdi? İki tarih" slaytı
