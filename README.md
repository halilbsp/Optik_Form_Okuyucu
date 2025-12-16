# 📝 Optik Form Okuyucu ve Puanlama Sistemi

### (Optical Mark Recognition – OMR)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![OpenCV](https://img.shields.io/badge/opencv-%23white.svg?style=for-the-badge&logo=opencv&logoColor=white)

Bu proje, **Python** ve **OpenCV** kullanarak optik formları (test/sınav kâğıtları) okuyan, cevapları algılayan, **otomatik puanlayan** ve sonuçları **Excel (.xlsx)** dosyasına kaydeden bir görüntü işleme uygulamasıdır.

> **Önemli Not:** Sistem, ışık değişimleri ve gölgelerden etkilenmemek için **Bağıl Koyuluk Algoritması (Relative Darkness Intensity)** kullanır. Sabit eşik yerine satır içi karşılaştırma yapar.

---

## 🚀 Özellikler

* **📷 Otomatik Algılama:** Kâğıdın köşe noktalarını bulur ve perspektif düzeltmesi (Bird’s Eye View) uygular.
* **🧠 Akıllı Cevap Okuma:** Her soruda en koyu şıkkı tespit eder; gölgeli/heterojen ışıkta dahi yüksek doğruluk sağlar.
* **✍️ Görsel İşaretleme:**

  * ✅ Doğru cevaplar **Yeşil**
  * ❌ Yanlış cevaplar **Kırmızı**
  * 🔵 Yanlış yapılan sorunun **doğru şıkkı Mavi**
* **📊 Raporlama:** Öğrenci numarası, doğru/yanlış sayıları ve puan; hem görüntü üzerine yazılır hem de **Excel** dosyasına eklenir.
* **🛡️ Hata Kontrolü:** Boş bırakılan ve **çoklu işaretlenen** sorular tespit edilir.

---

## 🛠️ Kurulum

### 1️⃣ Projeyi Klonlayın

```bash
git clone https://github.com/halilbsp/optik-form-okuyucu.git
cd optik-form-okuyucu
```

### 2️⃣ Gerekli Kütüphaneleri Yükleyin

```bash
pip install -r requirements.txt
```

> Alternatif manuel kurulum:

```bash
pip install opencv-python numpy matplotlib pandas openpyxl
```

---

## 💻 Kullanım

1. Okunacak optik form görselini proje klasörüne ekleyin (örn. `cevap.jpeg`).
2. `main.py` dosyasını çalıştırın:

```bash
python main.py
```

### 📌 Çıktılar

* İşlenmiş ve puanlanmış görsel: `Sonuc_<ogrenci_no>.jpg`
* Excel raporu: `Sinav_Sonuclari.xlsx`

---

## 📂 Proje Yapısı

```
├── main.py               # Ana kaynak kod
├── cevap.jpeg            # Okunacak örnek optik form
├── Sinav_Sonuclari.xlsx  # Otomatik oluşturulan Excel raporu
├── Sonuc_2212506062.jpg  # Örnek işlenmiş çıktı
├── requirements.txt      # Bağımlılıklar
└── README.md             # Proje dokümantasyonu
```

---

## ⚙️ Algoritma Mantığı

1. **Ön İşleme:** Görüntü gri tonlamaya çevrilir ve Gaussian Blur uygulanır.
2. **Kenar Tespiti:** Canny algoritması ile kâğıdın dış hatları bulunur.
3. **Perspektif Düzeltme:** Dört köşe tespit edilerek kuş bakışı görünüme dönüştürülür.
4. **Daire Tespiti:** Hough Circle Transform ile şık daireleri algılanır.
5. **Sıralama & Gruplama:** Daireler satır (soru) ve sütun (şık) bazında sıralanır.
6. **Cevap Analizi:** Her şıkkın piksel yoğunluğu ölçülür; satırdaki en koyu alan işaretli kabul edilir.
7. **Puanlama:** Sonuçlar cevap anahtarıyla karşılaştırılır ve Excel’e yazılır.

---

## 📸 Ekran Görüntüleri

![Sonuc_2212506062](https://github.com/user-attachments/assets/355ade2f-de3e-47de-a220-ca4b0d7f106f)


---

## 🤝 Katkıda Bulunma

1. Bu projeyi **Fork**’layın.
2. Yeni bir dal oluşturun:

   ```bash
   git checkout -b feature/YeniOzellik
   ```
3. Değişikliklerinizi commit edin:

   ```bash
   git commit -m "Yeni özellik eklendi"
   ```
4. Dalınızı push edin:

   ```bash
   git push origin feature/YeniOzellik
   ```
5. **Pull Request** oluşturun.

---

## 🎓 Teşekkür

Bu proje, **Dijital Görüntü Çözümleme** dersi kapsamında geliştirilmiştir. Değerli katkıları ve rehberliği için **Furkan Atlan** hocama teşekkür ederim.

---

## 👨‍💻 Geliştirici

**Halil BAŞPINAR**

![LinkedIn](https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white)    www.linkedin.com/in/halil-başpınar-0a7478384
