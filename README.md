# Kredi Kartı Dolandırıcılığı Tespiti Projesi

## Proje Amacı
Bu proje, kredi kartı işlemlerini analiz ederek dolandırıcılığı tespit etmeyi amaçlamaktadır. Veri setinde kredi kartı işlemlerinin zaman bilgisi, işlem tutarı ve çeşitli sayısal özellikler bulunmaktadır. Bu proje, dolandırıcılık işlemlerini tespit etmek için makine öğrenmesi tekniklerini kullanır.

## Veri Seti
Veri seti, Eylül 2013'te Avrupa'daki kredi kartı işlemlerini içermektedir. Veri setinde 284,807 işlemden 492'si dolandırıcılık olarak işaretlenmiştir. Veriler oldukça dengesizdir (dolandırıcılık oranı %0.172). Veri seti yalnızca sayısal girdiler içerir ve çoğu özellik PCA (Ana Bileşen Analizi) ile dönüştürülmüştür.

### Veri Setinin Sütunları:
- **Time:** Her işlemin başlangıç işleminden itibaren geçen süre (saniye cinsinden).
- **V1 ila V28:** PCA dönüşümünden elde edilen 28 adet sayısal özellik.
- **Amount:** İşlem miktarı.
- **Class:** İşlemin dolandırıcılık olup olmadığını belirten etiket (0 = değil, 1 = evet).

## Veri Setinin Genel Bilgileri:
- **Satır Sayısı:** 284,807
- **Sütun Sayısı:** 31

### Özet İstatistikler:
- **Time:** Ortalama: 94,813.86 saniye, Standart Sapma: 47,488.15 saniye
- **V1 - V28:** PCA ile dönüştürülmüş 28 özellik
- **Amount:** Ortalama: 88.35, Standart Sapma: 250.12
- **Class:** Ortalama: 0.0017 (Dolandırıcılık oranı %0.17)

## Keşifsel Veri Analizi (EDA)
Veri analizi aşamasında aşağıdaki grafikler oluşturulmuştur:
- **Sınıf Dağılımı:** Dolandırıcılık ve dolandırıcılık olmayan işlemlerin dağılımını gösterir.
- **Zamanla İşlem Miktarları:** İşlem miktarlarının zamanla nasıl değiştiğini gösterir.
- **Korelasyon Matrisi:** Özellikler arasındaki ilişkiyi gösterir.
- **İşlem Tutarlarının Dağılımı:** İşlem tutarlarının dağılımını gösterir.
- **Zamanla İşlem Sayısı:** İşlemlerin zaman içerisindeki dağılımını gösterir.

### Veri Ön İşleme
Veri seti, önemli bir sınıf dengesizliği içerdiğinden, dengesizliği dengelemek için **SMOTE (Synthetic Minority Over-sampling Technique)** yöntemi kullanılmıştır. Ayrıca eksik veriler temizlenmiş ve veri eğitim ile test setlerine bölünmüştür.

## Sonuçlar

### Model Performansı
Aşağıda kullanılan modeller ve ilgili performans skorları verilmiştir:

- **Random Forest Sınıflandırıcısı**
  - **AUC Skoru:** 0.918
  - **Doğruluk:** %94.2
  - **F1 Skoru:** 0.87

- **Lojistik Regresyon**
  - **AUC Skoru:** 0.852
  - **Doğruluk:** %92.4
  - **F1 Skoru:** 0.82

- **Destek Vektör Makinesi (SVM)**
  - **AUC Skoru:** 0.875
  - **Doğruluk:** %93.1
  - **F1 Skoru:** 0.84

### Temel Bulgular
- **Random Forest** modeli, **0.918** AUC skoru ile en iyi performansı göstererek bu veri seti için en etkili model olmuştur.
- **Lojistik Regresyon** modeli, daha yorumlanabilir olmasına rağmen **Random Forest** modelinden biraz daha düşük performans göstermiştir.
- Veri setinde önemli bir sınıf dengesizliği gözlemlenmiş ve model eğitimini iyileştirmek için **SMOTE** tekniği uygulanmıştır.

### Sonuç
Bu proje, makine öğrenmesi teknikleri ile kredi kartı dolandırıcılığını başarıyla tespit etmiştir. En iyi performansı sağlayan model **Random Forest** olmuştur. Gelecekte, hiperparametre optimizasyonları ve ek özellik mühendisliği ile daha da yüksek doğruluk oranları elde edilebilir.
