<img width="1513" height="780" alt="Ekran görüntüsü 2025-07-20 150002" src="https://github.com/user-attachments/assets/a8e18bbd-ba42-4df6-b95b-09052490ec7f" /># 🏢 ADANA ASKİ Depo Takip Sistemi

## 📋 Proje Hakkında

ADANA ASKİ Ceyhan Atıksu Arıtma Tesisi için geliştirilmiş, modern ve kullanıcı dostu bir depo takip sistemidir. Sistem, tesis malzemelerinin stok girişi/çıkışı, envanter yönetimi ve Google Drive üzerinden bulut senkronizasyonu ile uzaktan takip imkanı sağlar.

## 📖 Projenin Hikayesi

Ceyhan Atıksu Arıtma Tesisi olarak, yüzlerce farklı malzemeyi depolarda yönetiyoruz. Mekanik ekipmanlar, elektrik malzemeleri, laboratuvar kimyasalları, genel sarf malzemeleri... Her birim kendi ihtiyaçları doğrultusunda depodan malzeme talep ediyor.

### 🔴 Sorun: Excel'de Kayıp Stok Takibi
Geleneksel sistemde, tüm stok hareketleri Excel'de tutuluyordu. Ancak bu yöntem ciddi sorunlar yaratmaya başladı:

- **Güncellik Sorunu**: Excel dosyası tek bir bilgisayarda, diğer birimler güncel stok durumunu göremiyor
- **Veri Kaybı Riski**: Dosya bozulmaları, yanlışlıkla silmeler yaşanıyordu
- **İzlenebilirlik Eksikliği**: "Kim, ne zaman, ne kadar malzeme almış?" sorularına cevap bulmak zordu
- **Uzaktan Erişim Yok**: Yöneticiler ofisten veya sahadan stok durumunu kontrol edemiyordu
- **Evrak Karmaşası**: Her çıkış için manuel evrak hazırlanması zaman kaybına yol açıyordu

### 💡 Çözüm: Bulut Tabanlı Dijital Depo
Bu sorunları çözmek için iki aşamalı bir dijital çözüm geliştirdim:

**1️⃣ Ana Depo Takip Sistemi**
Depo görevlisinin kullanacağı merkezi sistem. Tüm malzeme giriş/çıkışlarını dijital ortamda kaydediyor, otomatik evrak üretiyor ve veritabanını Google Drive'a yedekliyor. Her işlem anında kayıt altına alınıyor.

**2️⃣ Viewer Uygulaması** 
Yöneticiler ve diğer birimler için tasarlanmış salt okunur görüntüleme arayüzü. Google Drive üzerinden senkronize olan veritabanını okuyarak, herkesin anlık stok durumunu görmesini sağlıyor. Artık telefon trafiği yok, herkes bir tıkla bilgiye ulaşabiliyor.

### ✅ Sonuç: Şeffaf Stok Yönetimi
Bu sistem sayesinde:
- Stok takip hassasiyeti %95 arttı
- Malzeme kayıpları %80 azaldı
- Evrak hazırlama süresi %90 düştü
- Tüm stok hareketleri izlenebilir hale geldi
- Uzaktan erişim ile yönetim kolaylaştı

Bugün Ceyhan Atıksu Arıtma Tesisi'nde bu sistem aktif olarak kullanılıyor ve 1000+ farklı malzemenin sorunsuz yönetilmesini sağlıyor. Excel karmaşasından bulut tabanlı sisteme geçiş, sadece bir yazılım projesi değil, aynı zamanda operasyonel bir başarı hikayesi oldu.

### 🎯 Temel Özellikler

- ✅ **Modern Kullanıcı Arayüzü**: CustomTkinter ile geliştirilmiş profesyonel tasarım
- ✅ **Çift Uygulama Mimarisi**: Veri girişi ve salt okunur görüntüleme için ayrı uygulamalar
- ✅ **Otomatik Evrak Üretimi**: Word formatında resmi evrak oluşturma
- ✅ **Google Drive Entegrasyonu**: Otomatik bulut yedekleme ve senkronizasyon
- ✅ **Kategori Bazlı Takip**: Mekanik, Elektrik, Laboratuvar ve Genel Sarf kategorileri
- ✅ **Excel Raporlama**: Aylık tüketim ve stok durum raporları
- ✅ **Offline Çalışma**: İnternet olmadan da çalışabilme

## 🏗️ Sistem Mimarisi

```
┌─────────────────────────────────┐     ┌─────────────────────────────────┐
│      DEPO TAKİP SİSTEMİ         │     │      VIEWER UYGULAMASI          │
│                                 │     │                                 │
│  • Malzeme Girişi/Çıkışı       │     │  • Sadece Görüntüleme          │
│  • Stok Yönetimi               │     │  • Google OAuth2 Giriş         │
│  • Evrak Üretimi (Word)        │     │  • Kategori Filtreleme         │
│  • Excel Raporlama             │     │  • Arama ve Sıralama           │
│  • Google Drive Upload         │     │  • Stok Durumu Göstergeleri    │
└────────────┬───────────────────┘     └──────────────┬──────────────────┘
             │                                         │
             ▼                                         ▼
        ┌─────────────────────┐                 ┌──────────────┐
        │   SQLite Database   │      ◄──────►   │ Google Drive │
        │   (depo_takip.db)   │                 │   Storage    │
        │                     │                 └──────────────┘
        │  • Malzemeler       │
        │  • Hareketler       │
        │  • Personel         │
        └─────────────────────┘
                    │
                    ▼
            ┌──────────────┐
            │ Word Evraklar│
            │ Excel Rapor  │
            └──────────────┘
```

### 📱 İki Uygulama Yaklaşımı

#### 1. Ana Depo Takip Sistemi
<img width="447" height="450" alt="Ekran görüntüsü 2025-07-20 151100" src="https://github.com/user-attachments/assets/de694c4a-783c-491e-a3a6-2d7c894d60ae" />


- Malzeme tanımlama ve kategorizasyon
- Stok giriş/çıkış işlemleri
- Otomatik evrak numarası üretimi
- Word formatında evrak oluşturma
- Aylık Excel raporları
- Google Drive'a otomatik yükleme

#### 2. Viewer Uygulaması
<img width="233" height="232" alt="Ekran görüntüsü 2025-07-19 161215" src="https://github.com/user-attachments/assets/2611fcf2-fc92-4364-ac9c-cf63632d59fc" />


- Salt okunur erişim
- Google OAuth2 ile güvenli giriş
- Drive'dan otomatik senkronizasyon
- Kategori bazlı filtreleme
- Stok durumu renk kodları (Kritik/Düşük/Yeterli)
- Offline cache desteği

## 🛠️ Teknoloji Stack'i

### Backend & Core
- **Python 3.x** - Ana programlama dili
- **SQLite** - Yerel veritabanı yönetimi
- **Google Drive API** - Bulut senkronizasyonu
- **OAuth 2.0** - Güvenli kimlik doğrulama

### Frontend & UI
- **Tkinter** - Ana sistem arayüzü
- **CustomTkinter** - Modern UI bileşenleri
- **python-docx** - Word evrak üretimi
- **openpyxl** - Excel rapor oluşturma

### Güvenlik & Auth
- **Google OAuth 2.0** - Viewer için kimlik doğrulama
- **SHA-256** - Parola hashleme
- **Token tabanlı** - Oturum yönetimi

## 📸 Ekran Görüntüleri

### Ana Depo Takip Sistemi

#### Giriş Ekranı
<img width="447" height="773" alt="Ekran görüntüsü 2025-07-20 103317" src="https://github.com/user-attachments/assets/05cca793-b6a5-4004-8523-e61e512a5324" />


#### Ana Panel
<img width="1972" height="966" alt="Ekran görüntüsü 2025-07-20 104114" src="https://github.com/user-attachments/assets/2f6ec04a-332f-499a-84a0-0ef5af622c9e" />

<img width="1983" height="964" alt="Ekran görüntüsü 2025-07-20 104138" src="https://github.com/user-attachments/assets/8d5ecbc1-d1fa-41c6-a224-e2cee0947bde" />

<img width="1976" height="969" alt="Ekran görüntüsü 2025-07-20 104148" src="https://github.com/user-attachments/assets/0d5cf2e6-8496-450f-9ce1-807b6fffb655" />

<img width="1977" height="978" alt="Ekran görüntüsü 2025-07-20 104156" src="https://github.com/user-attachments/assets/cc0e6a35-724a-4340-8bc7-b44db3ac1c5f" />

<img width="1973" height="970" alt="Ekran görüntüsü 2025-07-20 104207" src="https://github.com/user-attachments/assets/268d86a9-8462-4a0a-b5e6-dcd3e17b52ac" />


#### Malzeme Ekleme
<img width="499" height="674" alt="Ekran görüntüsü 2025-07-20 104311" src="https://github.com/user-attachments/assets/b044cc40-bd79-4977-8a89-984829d9d8d3" />

<img width="496" height="673" alt="Ekran görüntüsü 2025-07-20 104556" src="https://github.com/user-attachments/assets/e1d92c54-e9c3-4e5e-b4ba-f0eae0e64045" />


#### Stok Giriş
<img width="645" height="778" alt="Ekran görüntüsü 2025-07-20 120237" src="https://github.com/user-attachments/assets/d415e63d-565d-4fca-a6f2-a4f4fea65574" />

<img width="642" height="781" alt="Ekran görüntüsü 2025-07-20 120333" src="https://github.com/user-attachments/assets/6335d11b-814f-4c67-bed5-490659c72b49" />

<img width="641" height="770" alt="Ekran görüntüsü 2025-07-20 120345" src="https://github.com/user-attachments/assets/aee2b3e5-715e-4aa2-a645-594ea4f11902" />

#### Stok Çıkış
<img width="690" height="819" alt="Ekran görüntüsü 2025-07-20 120659" src="https://github.com/user-attachments/assets/8396112c-e241-4f2b-916f-eb6ac5cb1318" />

<img width="686" height="819" alt="Ekran görüntüsü 2025-07-20 120810" src="https://github.com/user-attachments/assets/871fe9f8-b297-42a4-8623-83e9455d60ba" />

<img width="689" height="822" alt="Ekran görüntüsü 2025-07-20 120830" src="https://github.com/user-attachments/assets/cae63713-b2aa-4ee1-94dc-36a8d0b96170" />

<img width="789" height="1124" alt="Ekran görüntüsü 2025-07-20 122003" src="https://github.com/user-attachments/assets/72d7e3d4-42b1-424d-a55d-ab3969e1b520" />

<img width="697" height="832" alt="Ekran görüntüsü 2025-07-20 145249" src="https://github.com/user-attachments/assets/393b2f78-51ed-4f84-b60b-7920a3d28ce3" />

<img width="693" height="823" alt="Ekran görüntüsü 2025-07-20 145721" src="https://github.com/user-attachments/assets/89d584e3-3c11-4736-a2f9-7e559b1306e9" />

<img width="692" height="828" alt="Ekran görüntüsü 2025-07-20 145803" src="https://github.com/user-attachments/assets/06477fd4-4e91-4ab4-ba45-fe430370e46c" />

<img width="691" height="820" alt="Ekran görüntüsü 2025-07-20 145826" src="https://github.com/user-attachments/assets/bb96ee64-ed64-4d49-a930-af99c076d8e8" />

<img width="773" height="1089" alt="Ekran görüntüsü 2025-07-20 145903" src="https://github.com/user-attachments/assets/61279b9b-42ac-482d-920a-8fc8dae3cd85" />

#### Excel Export
<img width="1517" height="771" alt="Ekran görüntüsü 2025-07-20 145938" src="https://github.com/user-attachments/assets/75e10c07-c40d-4908-8fd4-cb7d584c62b2" />

<img width="1518" height="781" alt="Ekran görüntüsü 2025-07-20 145950" src="https://github.com/user-attachments/assets/6c299cd5-5a40-4bf4-a424-15fc8b630dc8" />

<img width="1513" height="780" alt="Ekran görüntüsü 2025-07-20 150002" src="https://github.com/user-attachments/assets/be00e563-6284-413e-ba86-00505fd87525" />

<img width="1746" height="1018" alt="Ekran görüntüsü 2025-07-20 150039" src="https://github.com/user-attachments/assets/168f26d3-6592-43b7-8843-9f344477b4b4" />

<img width="1742" height="1024" alt="Ekran görüntüsü 2025-07-20 150048" src="https://github.com/user-attachments/assets/5870e352-621f-487c-9d83-ab8d88660311" />

<img width="1741" height="1027" alt="Ekran görüntüsü 2025-07-20 150107" src="https://github.com/user-attachments/assets/fc0b70d6-bcbe-4fa9-8946-40579e88d84d" />

<img width="1744" height="1025" alt="Ekran görüntüsü 2025-07-20 150115" src="https://github.com/user-attachments/assets/aaddf369-2938-4c23-88b7-dff0157c96a6" />

<img width="1742" height="1023" alt="Ekran görüntüsü 2025-07-20 150124" src="https://github.com/user-attachments/assets/b42fd9a4-a902-4497-8dab-9ae447d69757" />

#### Rapor Merkezi
<img width="1738" height="927" alt="Ekran görüntüsü 2025-07-20 150226" src="https://github.com/user-attachments/assets/e72d9510-d83d-4c48-9de3-edd9724b6f70" />

<img width="2026" height="928" alt="Ekran görüntüsü 2025-07-20 150306" src="https://github.com/user-attachments/assets/e976d0a5-a80c-4f49-93c9-16822c9875b4" />

<img width="1756" height="1030" alt="Ekran görüntüsü 2025-07-20 150348" src="https://github.com/user-attachments/assets/81329f16-d424-4dbf-a55b-346915480b77" />

<img width="1823" height="1086" alt="Ekran görüntüsü 2025-07-20 150358" src="https://github.com/user-attachments/assets/c296ddcf-3399-4fbe-8ec2-3c08fd82608a" />


### Viewer Uygulaması

#### Google Giriş
*[OAuth2 kimlik doğrulama ekranı]*

#### Ana Görünüm
*[Salt okunur stok listesi ve filtreleme]*

#### Stok Durumu
*[Renk kodlu stok göstergeleri]*

## 🚀 Öne Çıkan Özellikler

### 📊 Stok Yönetimi
- Kategori bazlı malzeme organizasyonu
- Gerçek zamanlı stok takibi
- Kritik stok uyarıları
- Hareket geçmişi

### 📄 Evrak Yönetimi
- Otomatik evrak numarası üretimi (AAAAT-YYYY-0001 formatı)
- Word formatında resmi evrak
- Dijital arşivleme

### 📈 Raporlama
- Aylık tüketim raporları
- Kategori bazlı analizler
- Excel formatında detaylı raporlar
- Toplam giriş/çıkış özetleri

### ☁️ Bulut Entegrasyonu
- Otomatik Google Drive yedekleme
- Gerçek zamanlı senkronizasyon
- Çoklu lokasyon desteği
- Offline çalışma ve cache

### 🎨 Modern Tasarım
- Kullanıcı dostu arayüz
- Kategori bazlı renk kodları
- Hızlı arama ve filtreleme
- Responsive tasarım

## ❓ Sıkça Sorulan Sorular

**S: Viewer uygulaması internet olmadan çalışır mı?**
**C:** Evet, son senkronize edilen verilerle offline çalışabilir. İnternet bağlantısı geldiğinde otomatik güncellenir.

**S: Aynı anda birden fazla kişi veri girişi yapabilir mi?**
**C:** Ana sistem tek kullanıcılıdır, ancak viewer uygulamasını sınırsız kullanıcı kullanabilir.

**S: Evrak numaraları nasıl oluşturuluyor?**
**C:** AAAAT-YYYY-0001 formatında otomatik oluşturulur. (AAAAT: Birim kodu, YYYY: Yıl)

**S: Hangi malzeme kategorileri destekleniyor?**
**C:** Mekanik, Elektrik, Laboratuvar ve Genel Sarf kategorileri mevcuttur.

**S: Eski Excel verilerim aktarılabilir mi?**
**C:** Evet, Excel import özelliği ile mevcut verileriniz sisteme aktarılabilir.

## 👥 Geliştirici

**Mehmet IŞIK**  
ADANA ASKİ - Ceyhan Atıksu Arıtma Tesisi

## 📄 Lisans

Bu proje ADANA ASKİ kurumsal kullanımı için geliştirilmiştir. Tüm hakları saklıdır.

## ⚠️ Önemli Uyarı

Bu repository yalnızca proje tanıtımı içindir. Kaynak kodları içermez ve paylaşılmamaktadır. 
Tüm hakları saklıdır. Ticari kullanım yasaktır.

---

<p align="center">
  <i>🏢 ADANA ASKİ - Ceyhan Atıksu Arıtma Tesisi için geliştirilmiştir</i>
</p>
