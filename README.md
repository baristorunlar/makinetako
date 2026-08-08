# İş Makinesi Takip & Cari Hesap Sistemi (Bulut Veritabanı)

Bu proje, İş Makinesi Takip ve Cari Hesap Yönetimi için tasarlanmış kurumsal web uygulamasıdır. 
Google Firebase Firestore ile **ücretsiz bulut veritabanı** entegrasyonuna sahiptir ve **GitHub Pages** üzerinde tek kuruş ödemeden yayınlanabilir.

---

## 🛠️ 1. Adım: Firebase Ücretsiz Veritabanını Oluşturma (2 Dakika)

1. [Google Firebase Console](https://console.firebase.google.com/) adresine gidin ve Google hesabınızla giriş yapın.
2. **"Proje Ekle" (Add Project)** butonuna tıklayın:
   - Proje adı girin (Örn: `is-makinesi-takip`) ve **Devam et** diyerek projeyi oluşturun.
3. Sol menüden **Build (Oluştur)** > **Firestore Database** sekmesine tıklayın.
4. **"Veritabanı Oluştur" (Create database)** butonuna basın:
   - Konum olarak size en yakın bölgeyi (Örn: `eur3 - Europe`) seçin.
   - **Test modunda başlat (Start in test mode)** seçeneğini işaretleyip **Oluştur** butonuna tıklayın.
5. Proje genel bakışına dönmek için sol üstteki ⚙️ **Proje Ayarları (Project Settings)** simgesine tıklayın.
6. Sayfanın en altındaki **"Uygulama Ekle" (Add app)** bölümünden `Web` `</>` simgesine tıklayın.
7. Uygulamaya bir isim verin (Örn: `is-makinesi-web`) ve **Uygulamayı Kaydet** butonuna basın.
8. Ekrana gelen `const firebaseConfig = { ... }` kod bloğundaki değerleri kopyalayın.

---

## 🔑 2. Adım: API Anahtarını Projeye Ekleme

1. Projenizdeki `firebase-config.js` dosyasını açın.
2. Kopyaladığınız değerleri aşağıdaki gibi yapıştırıp kaydedin:

```javascript
export const firebaseConfig = {
    apiKey: "AIzaSy...",
    authDomain: "is-makinesi-takip.firebaseapp.com",
    projectId: "is-makinesi-takip",
    storageBucket: "is-makinesi-takip.appspot.com",
    messagingSenderId: "123456789...",
    appId: "1:123456789...:web:abcdef..."
};
```

> **Not:** `firebase-config.js` dosyasına anahtarlarınızı girene kadar uygulama güvenlik amaçlı **Yerel Mod (localStorage)** ile çalışır. Anahtarları eklediğiniz an otomatik olarak **Bulut Veritabanı** moduna geçer.

---

## 🌐 3. Adım: GitHub Pages Üzerinden Ücretsiz Yayınlama

1. [GitHub.com](https://github.com) üzerinde yeni bir repository (depo) oluşturun (Örn: `is-makinesi-takip`).
2. Bu klasördeki tüm dosyaları (`index.html`, `firebase-config.js`, `README.md`) GitHub deponuza yükleyin (upload files veya `git push`).
3. Depo ayarlarından **Settings** > **Pages** sekmesine gidin.
4. **Build and deployment** kısmında **Source** olarak `Deploy from a branch` seçin ve `main` (veya `master`) dalını seçip **Save** butonuna basın.
5. 1-2 dakika içinde uygulamanız `https://kullaniciadi.github.io/is-makinesi-takip` adresinde canlıya alınacaktır!

---

## 📱 Özellikler

- **Çoklu Cihaz Desteği:** Masaüstü, tablet ve mobil cihazlardan canlı senkronizasyon.
- **Güvenlik:** Yetkisiz silme işlemlerini engellemek için 2 haneli doğrulama kodu ve giriş şifresi koruması.
- **Detaylı Excel Raporu:** 3 farklı sayfadan oluşan (Cari Hesap Özeti, Çalışma Hareketleri, Tahsilat Hareketleri) Excel indirme imkanı.
- **Çevrimdışı Çalışma:** İnternet koptuğunda veri kaybı yaşanmaz, bağlantı gelince Firebase ile eşitlenir.
