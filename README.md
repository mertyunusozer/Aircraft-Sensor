Makine Öğrenmesi ile Kalan Kullanım Ömrü (RUL) Tahmini

Bu proje, bir makine öğrenmesi projesi kapsamında Kalan Kullanım Ömrü (Remaining Useful Life, RUL) tahmini yapmak için geliştirilmiştir. Çalışmada çeşitli regresyon algoritmaları ve veri ön işleme teknikleri uygulanmıştır.

Veri seti, makine operasyon verilerini içermektedir. Her satır bir makine çalışması döngüsünü temsil eder ve hedef değişken olarak ilgili döngüdeki RUL değeri bulunur. Veri setinde şunlar yer almaktadır:

Ölçülen sayısal sensör değerleri,
Makine döngüsü bilgisi,
Makine kimliği (ID),
Hedef değişken: RUL,

Veri temizleme aşamasında:
Sabit sütunlar kontrol edilmiş,
Eksik veriler incelenmiş,
Gereksiz sütunlar (ör. ID, cycle) çıkarılmıştır.

Çalışma Adımları
Veri Keşfi ve Görselleştirme.
Korelasyon matrisi oluşturuldu.
RUL dağılımı ve log-dönüşümlü dağılım görselleştirildi.
Özellik önem grafikleri üretildi.

Ön İşleme
Standart ölçekleme (StandardScaler),
Polinomial özellikler oluşturma (PolynomialFeatures),
Log(1 + RUL) dönüşümü uygulanarak hedef değişken normalize edildi.

Modelleme
Aşağıdaki regresyon algoritmaları ayrı ayrı denenmiştir:
Linear Regression,
Ridge Regression,
Polynomial Regression + Ridge,
Random Forest Regressor,
XGBoost Regressor,
Her model için eğitim/test bölmesi (%80 eğitim - %20 test) sabit tutuldu.
Hiperparametre optimizasyonu için GridSearchCV kullanıldı.

Değerlendirme
Modeller R2, MAE, MSE ve RMSE metrikleri ile karşılaştırıldı.
Log dönüşümlü hedef değişken ile tahmin yapıldığında sonuçlar ters dönüşümle orijinal ölçeğe çevrildi.

Kullanılan Teknolojiler
Python,
NumPy, Pandas
scikit-learn,
XGBoost,
Matplotlib, Seaborn.

Sonuç
Bu proje, farklı regresyon modellerini ve hiperparametre aramalarını karşılaştırarak RUL tahmin performansını analiz etmeyi amaçlamaktadır. Kodun her aşaması modüler ve tekrarlanabilir şekilde düzenlenmiştir.
