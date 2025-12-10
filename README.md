📝 Optik Form Okuyucu ve Puanlama Sistemi
(Optical Mark Recognition - OMR System)
Bu proje, Python ve OpenCV kütüphanelerini kullanarak optik formları (test sınav kağıtlarını) tarayan, cevapları algılayan, otomatik puanlayan ve sonuçları Excel dosyasına kaydeden bir görüntü işleme uygulamasıdır.

Not: Bu proje, ışık değişimlerinden ve gölgelerden etkilenmemek için "Bağıl Koyuluk Algoritması" (Relative Darkness Intensity) kullanır.

🚀 Özellikler
📷 Otomatik Algılama: Kağıdın köşe noktalarını bulur ve perspektif düzeltmesi (Bird's Eye View) yapar.

🧠 Akıllı Cevap Okuma: Sabit bir siyahlık eşiği yerine, o satırdaki en koyu şıkkı analiz eder. Bu sayede gölgeli fotoğraflarda bile doğru sonuç verir.

✍️ Görsel İşaretleme:

✅ Doğru cevaplar Yeşil

❌ Yanlış cevaplar Kırmızı

🔵 Yanlış yapılan sorunun doğrusu Mavi ile işaretlenir.

📊 Raporlama: Öğrenci numarası, doğru/yanlış sayıları ve puan, resmin üzerine yazılır ve bir Excel (.xlsx) dosyasına otomatik olarak eklenir.

🛡️ Hata Kontrolü: Çift işaretlemeleri (Çoklu) ve boş bırakılan soruları tespit eder.

🛠️ Kurulum
Projeyi bilgisayarınızda çalıştırmak için aşağıdaki adımları izleyin.

1. Projeyi Klonlayın

git clone https://github.com/halilbsp/optik-form-okuyucu.git
cd optik-form-okuyucu

2. Gerekli Kütüphaneleri Yükleyin
Projenin çalışması için opencv-python, numpy, matplotlib, pandas ve openpyxl kütüphanelerine ihtiyaç vardır.

pip install opencv-python numpy matplotlib pandas openpyxl

💻 Kullanım
Okunacak optik form resmini proje klasörüne cevap.jpeg (veya kodda belirlediğiniz isimle) ekleyin.

main.py dosyasını çalıştırın:

python main.py
Program çalıştıktan sonra:

İşlenmiş ve puanlanmış resim Sonuc_OGRENCINO.jpg olarak kaydedilir.

Sonuçlar Sinav_Sonuclari.xlsx dosyasına satır olarak eklenir.

📂 Proje Yapısı
├── main.py              # Ana kaynak kod
├── cevap.jpeg           # Okunacak örnek optik form
├── Sinav_Sonuclari.xlsx # Otomatik oluşturulan Excel raporu
├── Sonuc_2212506062.jpg # İşlenmiş çıktı örneği
└── README.md            # Proje dökümantasyonu
⚙️ Nasıl Çalışır? (Algoritma Mantığı)
Ön İşleme: Görüntü gri tonlamaya çevrilir ve bulanıklaştırılır (Gaussian Blur).

Kenar Tespiti: Canny algoritması ile kağıdın dış hatları bulunur.

Perspektif Düzeltme: Kağıdın 4 köşesi tespit edilir ve kuş bakışı (dik) görünüme getirilir.

Daire Tespiti: Hough Circle Transform kullanılarak şıklar (daireler) tespit edilir.

Sıralama ve Gruplama: Bulunan daireler önce satırlara (sorulara), sonra sütunlara (şıklara) göre koordinat düzleminde sıralanır.

Cevap Analizi: Her şıkkın içindeki piksel yoğunluğu ölçülür. O satırdaki en koyu alan işaretlenmiş kabul edilir.

Puanlama: Tespit edilen şıklar, cevap anahtarı ile karşılaştırılır.

📸 Ekran Görüntüleri

<img width="303" height="619" alt="image" src="https://github.com/user-attachments/assets/c23b68d6-346f-457c-aefa-8a68aecbecb6" />

🤝 Katkıda Bulunma
Bu projeyi Fork'layın.

📄 Lisans
Bu proje MIT lisansı altında lisanslanmıştır.

👨‍💻 Geliştirici
Halil BAŞPINAR

GitHub: @halilbsp

LinkedIn: www.linkedin.com/in/halil-başpınar-0a7478384
