# Mikro Evren - Sonsuz Zoom ve Keşif Deneyimi

Mikro Evren, **Flutter** kullanılarak geliştirilmiş, "Deep Zoom" teknolojisini oyunlaştırarak sunan, 7 katmanlı bir keşif oyunudur. Kullanıcılar, ofis ortamından başlayıp evrenin mikro boyutlarına kadar uzanan gizli nesne bulma yolculuğuna çıkar.

---

## 🛠 Teknik Özellikler ve Mimari
* **Modüler Tasarım:** `GameLayer` ve `HiddenObject` sınıfları ile seviyelerin kolayca genişletilebilir veri odaklı yapısı.
* **Akış Güvenliği:** `_isLevelChanging` değişkeni ile seviye geçişleri sırasında hatalı etkileşimler engellenir.
* **Hata Yönetimi:** `currentLevelIndex` sınır kontrolleri sayesinde `IndexOutOfBounds` hatalarının önüne geçilmiştir.
* **Dinamik Performans:** `didChangeDependencies` metodu ile `precacheImage` kullanılarak görseller arka planda yüklenir ve akıcı bir geçiş sağlanır.
* **Responsive Yapı:** `LayoutBuilder` ile ekran boyutuna uyumlu, tüm cihazlarda kararlı çalışan arayüz.
* **Matematiksel Altyapı:** Nesne tespitlerinde hassasiyet için **Öklid Mesafesi** ($\sqrt{x^2 + y^2}$) formülü kullanılır.

## 📱 Oyun Mekanikleri
* **Zoom Sistemi:** `_zoomThreshold = 5.0` sınırı ile deneyim dengesi korunur.
* **Görsel Geçiş:** `Opacity` animasyonları ile katmanlar arası yumuşak geçiş.
* **Bitiş Diyaloğu:** 7. seviyeye ulaşıldığında kullanıcıyı karşılayan kutlama ekranı.

## 🛠 Geliştirici (Admin) Modu
Geliştirme sürecini hızlandırmak için eklenmiştir:
* **Koordinat Dedektörü:** Tıklanan noktanın `Alignment(x, y)` değerini verir.
* **Görsel Rehber:** Bulunması gereken nesnelerin etrafında kırmızı halkalar oluşturur.
* **Kilit Bypass:** Nesne bulma zorunluluğunu kaldırarak seviyeler arasında hızlı geçiş sağlar.

## Görseller
<img width="461" height="809" alt="image" src="https://github.com/user-attachments/assets/8506258d-338b-4ca1-8a05-fdd1d9072c03" />
<img width="458" height="809" alt="image" src="https://github.com/user-attachments/assets/59b79b77-ff33-41a5-ad64-56db92714490" />
<img width="453" height="814" alt="image" src="https://github.com/user-attachments/assets/a73c1f5e-27c9-41c3-af45-371e89dd2d6c" />
<img width="455" height="811" alt="image" src="https://github.com/user-attachments/assets/59720035-3fd5-4c0a-abe9-f34a9abb5f74" />
<img width="455" height="808" alt="image" src="https://github.com/user-attachments/assets/089398df-1012-4743-ab10-a56da312016c" />
<img width="455" height="809" alt="image" src="https://github.com/user-attachments/assets/bbdc9602-b4d8-49c9-bb4f-6c579458271c" />
<img width="458" height="808" alt="image" src="https://github.com/user-attachments/assets/a6d42f4a-659d-4608-8fba-50d1ef89f4f5" />

## 📂 Dosya Yapısı
```text
lib/main.dart  // Ana oyun mantığı, State yönetimi ve etkileşimler
assets/        // Seviye görsel kaynakları
├── level_1.png
├── ...
└── level_7.png
