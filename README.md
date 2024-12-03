# Kardiyovasküler Hastalıkların Teşhisi İçin Yapay Zekâ Sınıflandırıcı Modeli

## Proje Amacı
Bu proje, kardiyovasküler hastalıkların erken teşhisini yapabilecek bir yapay sinir ağı modeli geliştirmeyi amaçlamaktadır. Kardiyovasküler hastalıklar dünya çapında önde gelen ölüm nedenlerinden biridir ve her yıl yaklaşık 17.9 milyon kişinin ölümüne yol açmaktadır. Erken teşhis, bu hastalıkların önlenmesi veya etkilerinin azaltılması açısından kritik bir rol oynar. 

Geliştirilen yapay sinir ağı modeli, bireylerin sağlık verilerini analiz ederek kardiyovasküler hastalık risklerini tahmin etmeyi hedefler. Proje kapsamında, modelin performansını artırmak için çeşitli eğitim stratejileri ve çapraz doğrulama yöntemleri test edilmiştir.

---

## Sınıflandırma Amacı
Projenin amacı, veri setinde bulunan bireylerin sağlık durumlarına ve risk faktörlerine dayanarak kalp hastalığına sahip olup olmadıklarını sınıflandırmaktır.  
**Hedef Sınıf:**
- `HeartDisease`: 
  - `1`: Kalp hastalığı var
  - `0`: Kalp hastalığı yok

---

## Veri Seti
Proje, Kaggle platformunda sunulan **Heart Failure Prediction Dataset** isimli veri seti kullanılarak gerçekleştirilmiştir. Veri seti, kardiyovasküler hastalık tahmini için hazırlanmış, 5 farklı kaynaktan derlenerek 11 özellik içeren 918 örnekten oluşmaktadır.

### Özellikler
Veri setindeki bağımsız değişkenler ve hedef sınıf aşağıdaki gibidir:

| Özellik Adı       | Açıklama                                                                                  |
|--------------------|------------------------------------------------------------------------------------------|
| **Age**           | Hastanın yaşı (yıl).                                                                     |
| **Sex**           | Hastanın cinsiyeti (M: Erkek, F: Kadın).                                                 |
| **ChestPainType** | Göğüs ağrısı türü (TA, ATA, NAP, ASY).                                                   |
| **RestingBP**     | Dinlenme kan basıncı (mm Hg).                                                            |
| **Cholesterol**   | Serum kolesterol düzeyi (mg/dl).                                                         |
| **FastingBS**     | Açlık kan şekeri (1: >120 mg/dl, 0: ≤120 mg/dl).                                         |
| **RestingECG**    | Dinlenme elektrokardiyogram sonuçları (Normal, ST, LVH).                                 |
| **MaxHR**         | Maksimum kalp hızı (60-202 arası sayısal değer).                                         |
| **ExerciseAngina**| Egzersiz kaynaklı anjina (Y: Evet, N: Hayır).                                            |
| **Oldpeak**       | ST segment depresyonu (sayısal değer).                                                   |
| **ST_Slope**      | Egzersiz ST segmenti eğimi (Up, Flat, Down).                                             |

### Örnek Sayısı
Toplamda 918 örnek bulunmaktadır. Veri seti şu kaynaklardan derlenmiştir:
- **Cleveland**: 303 gözlem
- **Hungarian**: 294 gözlem
- **Switzerland**: 123 gözlem
- **Long Beach VA**: 200 gözlem
- **Stalog (Heart) Data Set**: 270 gözlem  
Tekrarlayan 272 veri çıkarılmıştır.

---

## Model ve Uygulama Stratejileri
Model, yapay sinir ağı (ANN) mimarisi ile oluşturulmuş ve çeşitli eğitim stratejileri uygulanmıştır:

1. **Eğitim setini aynı zamanda test verisi olarak kullanarak eğitim**
   - Eğitim ve test verilerinin aynı olması durumunda modelin doğruluk ve kayıp sonuçları analiz edilmiştir.
   - Modelin genelleme performansını değerlendirmek için önerilmez, ancak başlangıç denemeleri için kullanılmıştır.

2. **5-Fold Cross Validation (5 Katlı Çapraz Doğrulama)**
   - Veri seti 5 eşit parçaya ayrılarak model her bir fold üzerinde eğitilip test edilmiştir.
   - Ortalama doğruluk ve kayıp sonuçları:
     - **Mean Accuracy**: %85.29
     - **Mean Loss**: %49.05

3. **10-Fold Cross Validation (10 Katlı Çapraz Doğrulama)**
   - Benzer şekilde, veri seti 10 eşit parçaya bölünerek çapraz doğrulama yapılmıştır.
   - Daha ayrıntılı analiz ve daha az varyans sağlamak amacıyla uygulanmıştır.

4. **%66 - %34 Eğitim ve Test Ayrımı**
   - Veri seti, %66 eğitim ve %34 test olarak rastgele bölünmüştür.
   - Rastgele bölünme işlemi 5 kez tekrar edilerek sonuçlar karşılaştırılmıştır.

---
Kaynaklar
Kaggle Heart Failure Prediction Dataset
UCI Machine Learning Repository
Copy code




