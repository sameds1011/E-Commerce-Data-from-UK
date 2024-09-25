# E-Commerce-Data-from-UK
Müşteri Satın Alma Analizi Raporu
1. Giriş
Bu projede, bir e-ticaret platformu üzerindeki müşteri satın alma verileri incelenmiştir. 
Hedefimiz, müşteri davranışlarını analiz etmek, en çok satılan ürünleri belirlemek ve müşteri segmentasyonuna göre harcama eğilimlerini incelemektir.
 Analiz boyunca eksik veri temizleme, veri dönüşümleri ve sınıflandırma modelleri gibi çeşitli yöntemler kullanılmıştır.



2. Veri Ön İşleme
Eksik Veriler: CustomerID sütununda %25 oranında eksik veri bulundu. Bu sütundaki eksik veriler, ilgili satırların model performansını olumsuz etkileyebileceği 
gerekçesiyle silindi dropna. Ayrıca, Description sütunundaki eksik veriler, basit bir string değeri ile dolduruldu fillna.

Veri Dönüşümleri: Veriyi anlamlı hale getirebilmek için TotalRevenue isimli yeni bir sütun oluşturuldu. Bu sütun, her bir satın alma işlemi için 
Quantity ve UnitPrice çarpılarak hesaplanmıştır. Müşteri bazında harcamaları analiz edebilmek için aylık ve yıllık satış verileri de türetilmiştir.


3. Keşifsel Veri Analizi (EDA)
En Çok Satılan İlk  Ürünler: Analiz sonucunda en çok satılan ürünlerin listesi aşağıdaki gibidir:Gelecekte bu ürünlere talep artıcaktır.

Ürün Adı	                                Satış Miktarı
WHITE HANGING HEART T-LIGHT HOLDER	             5367
REGENCY CAKESTAND 3 TIER	                       4736
JUMBO BAG RED RETROSPOT	                         4634
PARTY BUNTING	                                   4566
ASSORTED COLOUR BIRD ORNAMENT	                   4246


Popüler Ürün Kategorileri: Veriler incelendiğinde, özellikle ev dekorasyonu ve mutfak gereçleri kategorilerinin en popüler olduğu görülmüştür. 
Müşteri harcamalarının büyük bir kısmı bu kategorilere yönelmiştir.Bu analiz için ürün açıklamalarına göre kategorilere ayırma işlemide yapılabilir.


Müşteri Segmentasyonu: Müşteri harcamaları analiz edildiğinde, en yüksek harcamayı yapan müşteri gruplarının genellikle yıllık harcaması 5000 TL’nin üzerinde olan 
sadık müşteriler olduğu tespit edilmiştir. Bu müşteriler, toplam gelirde büyük bir paya sahiptir ve onlara yönelik özel kampanyalar düzenlemek gelirleri artırabilir.



Modelleme ve Sonuçlar
Logistic Regression ve Random Forest Modelleri: İki farklı model kullanılmıştır: Logistic Regression ve Random Forest.

Logistic Regression, basit bir model olup, sınıflandırma başarısı %99,95 olarak hesaplanmıştır.

Random Forest modeli, daha güçlü bir modeldir ve %99,99’luk bir doğruluk oranına ulaşmıştır. 

Özellikle sınıf dengesizliği olan veri setlerinde Random Forest, daha dengeli sonuçlar üretmiştir.o yüzden random tercih ettim.



 Sonuçlar ve Öneriler
En Çok Satılan Ürünler: Analiz sonucunda en çok satılan ürünlerin ev dekorasyonu ve mutfak gereçleri olduğu tespit edilmiştir. 
Bu kategorilere yönelik kampanyalar veya stok artırımı yapılabilir.

Müşteri Segmentasyonu: Sadık müşterilere özel kampanyalar düzenlenmesi, satışların artmasına yardımcı olabilir.
 Örneğin, yüksek harcama yapan müşterilere yönelik kişiselleştirilmiş indirimler veya ödül programları oluşturulabilir.


Öneriler:

En çok satılan ürünlerin stok yönetiminin daha iyi yapılması.
Sadık müşterilere yönelik e-posta kampanyalarının artırılması.
Popüler ürün kategorilerine yönelik reklam stratejilerinin geliştirilmesi.




Sonuç
Bu projede müşteri satın alma verileri üzerinde yapılan analizler, müşteri segmentasyonu ve ürün popülaritesi gibi önemli bulgular ortaya koymuştur.

Elde edilen sonuçlar ışığında önerilen stratejiler, gelecekteki satışların artırılmasına yardımcı olur


Veri Setindeki düzeltmeler


Müşteri harcamaları arasında büyük bir dengesizlik olabilir
Yani, 1000 TL’nin üzerinde harcama yapan müşteri sayısı, altındaki müşterilere göre çok daha az olabilir.
 Bu, modelin performansını olumsuz etkileyebilir.
 Dengesiz veri, modelin daha az sayıda bulunan sınıfı doğru tahmin etmesini zorlaştırır ve genellikle ağırlıklı olarak çoğunluk sınıfını tahmin eder.


Çözüm: Bu durumu çözmek için SMOTE gibi yöntemler kullanarak veri setini dengelesemde yine de dikkat edilmesi gereken bir durum.

Model Performansı:

İlk Logistic Regression sonuçlarına göre, bazı aşamalarda recall ve precision gibi metriklerin düşük çıktığını gördüm.
Özellikle daha az harcama yapan müşterileri doğru tahmin etmede modelin zorlandığını fark ettim.
Bu yüzden kaldırıp  Random Forest kullandım hiperparametre optimizasyonu yapmak veya daha fazla özellik eklemek performansı artırabildigi için kullandım.


Eksik Veriler:

Veride bazı eksik değerler vardı CustomerID ve Description değişkenlerinde. 
Bu eksiklikleri doldurup temizledim, Customer ID dropna yüzdeki oranı fazlaydı Description fiilna ile dolduruldu yüzdelik oranı düşük oldugu için.
 
Başarılar:

Müşteri harcama alışkanlıklarını analiz ederek, en fazla harcama yapan müşteri gruplarını belirledim.
En çok satan ürün kategorilerini tanımlayarak, satış stratejilerini desteklemek için kullanılabilecek içgörüler sağladım.
Model doğruluğunu artırmak için Random Forest algoritması kullanarak yüksek performans elde ettim.



Kullanılan Teknolojiler:

Python: Veri analizi ve modelleme için temel programlama dili.
Pandas: Veri manipülasyonu ve analizi için kullanıldı.
Scikit-learn: Makine öğrenimi algoritmaları k-means (Lojistik Regresyon ve Random Forest) için kullanıldı.
Imbalanced-learn: Dengesiz veri setleri için SMOTE tekniği uygulandı.
Matplotlib & Seaborn: Veri görselleştirmeleri için kullanıldı.







Yapılan Tahminler:
Müşteri Satın Alma Eğilimleri:

Hedef Değişken: Müşterilerin toplam harcaması 1000 TL’yi aşıp aşmayacağı tahmin edildi.
Model Kullanımı: Logistic Regression ve Random Forest gibi modeller kullanarak, belirli müşteri gruplarının gelecekteki satın alma davranışlarını tahmin ettik.
Ürün Popülaritesi:
En çok satılan ürünlerin analizi yapıldı ve bu ürünlerin gelecekteki talebinin artacağı öngörüldü.

