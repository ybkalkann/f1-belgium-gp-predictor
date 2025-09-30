\# 🏎️ F1 Belgium GP 2025 Race Predictor



Makine öğrenmesi kullanarak Formula 1 Belçika Grand Prix yarış sonuçlarını tahmin eden kapsamlı bir analiz sistemi.



\## 📋 Proje Hakkında



Bu proje, 2024 sezonundan elde edilen gerçek telemetri verileri ve geçmiş performans istatistikleri kullanarak 2025 Belçika Grand Prix'sinin yarış sonuçlarını tahmin eder. Gradient Boosting Regressor modeli ile desteklenen sistem, aşağıdaki analizleri sunar:



\- 🏁 Sıralama ve yarış sıralaması tahminleri

\- 🛞 Lastik degradasyon analizi

\- 🔧 Pit stop strateji optimizasyonu

\- 🎯 Sollama olasılık matrisi

\- 🌤️ Hava durumu etkisi simülasyonu

\- 📊 Takım ve pilot performans karşılaştırması



\## ✨ Özellikler



\### 1. Yarış Tahmini

\- \*\*Veri Kaynağı\*\*: FastF1 kütüphanesi ile 2024 Belçika GP telemetri verileri

\- \*\*Model\*\*: Gradient Boosting Regressor (150 estimator, 0.1 learning rate)

\- \*\*Girdi Özellikleri\*\*: 

&nbsp; - Sıralama süresi

&nbsp; - Temiz hava yarış hızı

&nbsp; - Takım performans skoru

&nbsp; - Hava durumu koşulları (sıcaklık, yağış olasılığı)

&nbsp; - Ortalama pozisyon değişimi



\### 2. Lastik Stratejisi Analizi

\- Üç lastik bileşeni için degradasyon modelleme (Soft, Medium, Hard)

\- Sürücü bazlı lastik yönetimi becerileri

\- Sıcaklık etkisi simülasyonu

\- Optimal lastik seçimi önerileri



\### 3. Pit Stop Optimizasyonu

\- Tek ve çift pit stop stratejilerinin karşılaştırması

\- DRS ve undercut avantajı hesaplamaları

\- Güvenlik aracı olasılığı senaryoları

\- Spa-Francorchamps'a özel pit penceresi optimizasyonu



\### 4. Sollama Analizi

\- Sürücü bazlı atak/savunma yetenekleri

\- Araç performans farkı etkisi

\- DRS bölgesi avantajı hesaplamaları

\- Lastik avantajı senaryoları



\## 🚀 Kurulum



\### Gereksinimler

\- Python 3.8+

\- pip paket yöneticisi



\### Adımlar



1\. Repoyu klonlayın:

```bash

git clone https://github.com/kullaniciadi/f1-belgium-gp-predictor.git

cd f1-belgium-gp-predictor

```



2\. Sanal ortam oluşturun (önerilir):

```bash

python -m venv venv

source venv/bin/activate  # Windows: venv\\Scripts\\activate

```



3\. Gerekli paketleri yükleyin:

```bash

pip install -r requirements.txt

```



4\. OpenWeatherMap API anahtarı alın:

&nbsp;  - \[OpenWeatherMap](https://openweathermap.org/api) adresinden ücretsiz API anahtarı alın

&nbsp;  - `.env` dosyası oluşturun ve anahtarınızı ekleyin:

```

OPENWEATHER\_API\_KEY=your\_api\_key\_here

```



\## 💻 Kullanım



Temel kullanım:

```bash

python src/predict\_race.py

```



Program otomatik olarak:

1\. 2024 Belçika GP verilerini indirecek ve önbelleğe alacak

2\. Hava durumu tahminini çekecek

3\. Makine öğrenmesi modelini eğitecek

4\. 2025 tahminlerini oluşturacak

5\. Görselleştirmeleri gösterecek



\## 📊 Çıktılar



\### Konsol Çıktıları

\- Sıralama ve yarış sıralaması

\- Podyum tahminleri

\- Puan dağılımı

\- Lastik strateji analizi

\- Sollama istatistikleri



\### Görsel Analizler

\- Pozisyon değişim grafikleri

\- Takım performans karşılaştırmaları

\- Lastik degradasyon eğrileri

\- Sollama olasılık ısı haritaları

\- Zaman farkı görselleştirmeleri



\## 🔍 Metodoloji



\### Veri Toplama

\- \*\*Kaynak\*\*: 2024 Belçika Grand Prix (14. yarış)

\- \*\*Telemetri\*\*: FastF1 API

\- \*\*Hava Durumu\*\*: OpenWeatherMap API



\### Model Eğitimi

```python

GradientBoostingRegressor(

&nbsp;   n\_estimators=150,

&nbsp;   learning\_rate=0.1,

&nbsp;   max\_depth=4,

&nbsp;   random\_state=42

)

```



\### Özellik Mühendisliği

\- Sürücü performans faktörleri (subjektif değerlendirme)

\- Takım performans skorları (2024 sezonu puanlarına göre)

\- Islak performans düzeltmeleri

\- Spa-spesifik pozisyon değişim ortalamaları



\## 📈 Model Performansı



Model, geçmiş verilere dayanarak eğitilmiştir ve aşağıdaki faktörleri dikkate alır:

\- Sürücü yeteneği ağırlığı: %70

\- Takım performansı ağırlığı: %30

\- Hava durumu etkisi: Dinamik

\- Pist karakteristiği: Spa-Francorchamps optimizasyonu



\## 🛠️ Teknolojiler



\- \*\*FastF1\*\*: F1 telemetri verisi

\- \*\*scikit-learn\*\*: Makine öğrenmesi modeli

\- \*\*pandas/numpy\*\*: Veri işleme

\- \*\*matplotlib\*\*: Görselleştirme

\- \*\*requests\*\*: API entegrasyonu



\## 📝 Notlar



\- Tahminler geçmiş verilere ve istatistiksel modellere dayanır

\- Gerçek yarış sonuçları beklenmeyen faktörlerden etkilenebilir

\- Model sürekli geliştirilmekte ve iyileştirilmektedir



\## 🤝 Katkıda Bulunma



Katkılarınızı bekliyoruz! Lütfen:

1\. Fork yapın

2\. Feature branch oluşturun (`git checkout -b feature/YeniOzellik`)

3\. Değişikliklerinizi commit edin (`git commit -m 'Yeni özellik eklendi'`)

4\. Branch'inizi push edin (`git push origin feature/YeniOzellik`)

5\. Pull Request oluşturun



\## 📄 Lisans



Bu proje MIT lisansı altında lisanslanmıştır - detaylar için \[LICENSE](LICENSE) dosyasına bakın.



\## 👤 Yazar



\*\*\[Adınız]\*\*

\- GitHub: \[@kullaniciadi](https://github.com/kullaniciadi)

\- LinkedIn: \[Profiliniz](https://linkedin.com/in/profiliniz)



\## 🙏 Teşekkürler



\- FastF1 topluluğu - Harika telemetri kütüphanesi için

\- OpenWeatherMap - Hava durumu API'si için

\- Formula 1 - İlham için



\## 📸 Ekran Görüntüleri



\*(Burada proje çıktılarınızın ekran görüntülerini ekleyin)\*



---



⭐ Projeyi beğendiyseniz yıldız vermeyi unutmayın!

