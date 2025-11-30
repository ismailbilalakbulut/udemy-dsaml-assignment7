# 🌍 Udemy Veri Bilimi ve Makine Öğrenmesi: 100 Günlük Kamp — 7. Ödev: Kümeleme Analizi

Bu depo, Udemy’de aldığım *Makine Öğrenmesi Kursu* kapsamında verilen **7. ödev** için hazırlanmıştır. Bu ödevde, ülkelerin sosyo-ekonomik göstergelerine dayalı olarak kümelenmesi ve **Boyut İndirgeme (Dimensionality Reduction)** tekniği olan **Temel Bileşenler Analizi (PCA)**'nin kümeleme başarısı üzerindeki etkisi kapsamlı bir şekilde analiz edilmiştir.

---

## 🎯 Proje Amacı

### **Temel Amaç**
Farklı sosyo-ekonomik göstergelere sahip ülkeleri benzer özelliklerine göre anlamlı gruplara (kümelere) ayırmak ve bu gruplar arasındaki farklılıkları incelemektir.

### **Kritik Değerlendirme**
Kümeleme performansının; verinin **orijinal hali** ile **PCA uygulanmış hali** üzerinde nasıl değiştiğini gözlemlemek ve farklı kümeleme algoritmalarının (**K-Means**, **HDBSCAN**, **Hierarchical**) bu iki farklı veri seti üzerindeki etkinliğini karşılaştırmaktır.

---

## 🌷 Kullanılan Veri Seti

| Kriter | Detay |
| :--- | :--- |
| **Veri Seti** | 29-country_data.csv (Ülkelerin Sosyo-Ekonomik Göstergeleri) |
| **Problem Tipi** | Denetimsiz Öğrenme (Kümeleme) |
| **Örnek Değişkenler** | Child Mortality, Exports, Imports, Income, Gdpp, vb. |

---

## 🛠️ Proje Aşamaları ve Ön İşleme

Proje, kümeleme algoritmalarına girdi sağlamadan önce verinin kalitesini ve uygunluğunu artırmaya odaklanan kapsamlı temizlik ve dönüşüm aşamalarından oluşmuştur.

### 🔹 1. Veri Hazırlığı

- **Ön İşleme:** Veri setindeki potansiyel aykırı değerler ele alınmış ve veri setinin analiz için uygunluğu sağlanmıştır.
- **Ölçekleme (Scaling):** Tüm sayısal değişkenler, algoritmaların mesafeye dayalı çalışmasını sağlamak amacıyla **StandardScaler** kullanılarak standartlaştırılmıştır.

### 🔹 2. Boyut İndirgeme (Dimensionality Reduction)

- **Temel Bileşenler Analizi (PCA):** Yüksek boyutlu veri setinin temel varyansını koruyarak boyutunu düşürmek amacıyla PCA uygulanmıştır. Bu sayede hem hesaplama maliyeti azaltılmış hem de kümeleme performansına etkisi incelenmiştir.
- **Analiz İkiliği:** Kümeleme analizleri, karşılaştırma amacıyla hem ölçeklenmiş **orijinal veri seti** hem de **PCA uygulanmış veri seti** üzerinde ayrı ayrı yapılmıştır.

---

## 🔹 3. Uygulanan Kümeleme Algoritmaları

Analizler, ödev gereksinimleri doğrultusunda üç farklı kümeleme algoritması kullanılarak, PCA'nın etkisini görmek için her iki veri setinde de gerçekleştirilmiştir:

| Algoritma | Açıklama |
| :--- | :--- |
| **K-Means** | Merkez (centroid) tabanlı kümeleme. Optimal küme sayısı, **Elbow Metodu** ve **Silhouette Skoru** ile belirlenmiştir. |
| **HDBSCAN** | Yoğunluk tabanlı kümeleme (Density-Based). Aykırı değerlere ve gürültüye daha dirençli yapısı incelenmiştir. |
| **Hierarchical Clustering** | Hiyerarşik (Aglomeratif) kümeleme. **Dendrogram** görseli ile küme sayısının belirlenmesi ve küme yapısının derinlemesine incelenmesi sağlanmıştır. |

---

## ✅ Sonuçlar ve Performans Değerlendirmesi

Tüm modellerin karşılaştırmalı performans metrikleri (Silhouette Skoru ve Küme İçi Görsel Dağılım) kullanılarak değerlendirilmiştir.

### 📈 Temel Bulgular

1.  **PCA'nın Rolü:** PCA uygulaması, yüksek boyutluluğun getirdiği "boyutların laneti" etkisini azaltarak, özellikle **K-Means** ve **Hierarchical** kümelemede küme ayrımının daha belirgin hale gelmesine ve daha tutarlı Silhouette skorları elde edilmesine katkıda bulunmuştur.
2.  **Algoritma Farklılıkları:**
    * **K-Means**, küresel kümeler oluşturmada başarılı olmuş, ancak aykırı değerlere karşı hassasiyeti gözlemlenmiştir.
    * **HDBSCAN**, veri setindeki gürültüyü (ayıklanmamış aykırı değerleri) bir küme olarak sınıflandırmayarak daha esnek bir yapı sergilemiştir.
3.  **En İyi Performans:** **K-Means** algoritması, **PCA** veri seti üzerinde **en yüksek Silhouette Skoru** ile en iyi ayrımı sağlamıştır.
