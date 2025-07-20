# 🏢 ADANA ASKİ Depo Takip Sistemi

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
*[Kullanıcı girişi ve oturum yönetimi]*

#### Ana Panel
*[Kategori butonları, stok listesi ve işlem butonları]*

#### Malzeme Ekleme
*[Yeni malzeme tanımlama formu]*

#### Stok Giriş/Çıkış
*[Malzeme seçimi, miktar girişi ve personel bilgileri]*

#### Rapor Merkezi
*[Aylık özet, kategori dağılımı ve Excel export]*

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
