# Pirinç Görüntü Sınıflandırması | CNN | %99 Başarı

Bu proje, Akbank & Global AI Hub iş birliğiyle düzenlenen Derin Öğrenme Bootcamp'i kapsamında gerçekleştirilmiştir.

## 1. Giriş

### Proje Hedefi
Bu notebook'ta, 5 farklı pirinç türünü görsellerinden ayırt edebilen bir derin öğrenme modeli geliştirilecektir. Bu amaçla, Keras kütüphanesi kullanılarak sıfırdan bir **Evrişimli Sinir Ağı (CNN)** modeli oluşturulacak, eğitilecek ve performansı değerlendirilecektir.

### Veri Setine Genel Bakış
Çalışmada, her biri 15,000 adet görüntü içeren 5 farklı pirinç sınıfından oluşan dengeli bir veri seti kullanılmıştır. Görevimiz, bu 75,000 görüntülük veri setini kullanarak pirinç türlerini yüksek doğrulukla sınıflandırabilen bir model tasarlamaktır.

- **Veri Seti Linki:** [Rice Image Dataset](https://www.kaggle.com/datasets/muratkokludataset/rice-image-dataset)

### Sınıflandırılacak Pirinç Türleri
* Arborio
* Basmati
* Ipsala
* Jasmine
* Karacadag



## 2. Uygulanan Adımlar

Proje süresince, bir derin öğrenme modelinin geliştirilmesi için gereken temel adımlar izlenmiştir:

1.  **Veri Hazırlığı:** Veri seti yüklendi, keşif amaçlı görselleştirmeler yapıldı ve `ImageDataGenerator` ile veri çoğaltma (Data Augmentation) teknikleri uygulandı.
2.  **Model Mimarisi:** Görüntü işlemeye uygun, üç `Conv2D` bloğu ve `Dropout` katmanı içeren bir CNN modeli Keras ile oluşturuldu.
3.  **Model Eğitimi:** Model, `EarlyStopping` ve `ModelCheckpoint` gibi akıllı yardımcılar kullanılarak, aşırı öğrenmenin önüne geçilerek en verimli şekilde eğitildi.

---

## 3. Elde Edilen Sonuçlar

Yapılan eğitim ve değerlendirmeler sonucunda, modelin oldukça başarılı olduğu görülmüştür.

### 3.1. Performans Metrikleri
- Model, daha önce görmediği doğrulama verileri üzerinde **%99 genel doğruluk (`accuracy`)** oranına ulaşmıştır.
- Sınıflandırma Raporu ve Karışıklık Matrisi, modelin tüm pirinç türlerini neredeyse hatasız bir şekilde ayırt edebildiğini göstermektedir.

Classification Report

              precision    recall  f1-score   support

     Arborio       0.98      0.98      0.98      3000
     Basmati       1.00      0.98      0.99      3000
      Ipsala       0.99      1.00      1.00      3000
     Jasmine       0.97      1.00      0.98      3000
   Karacadag       1.00      0.98      0.99      3000
   
    accuracy                           0.99     15000
   macro avg       0.99      0.99      0.99     15000
weighted avg       0.99      0.99      0.99     15000


<img width="797" height="703" alt="__results___21_1" src="https://github.com/user-attachments/assets/0d2511c4-0d68-49b5-8784-13c90e0242b7" />


### 3.2. Öğrenme Süreci ve Yorumlama
- **Öğrenme Grafikleri:** Doğruluk ve kayıp grafikleri, modelin aşırı öğrenme olmadan stabil bir şekilde öğrendiğini doğrulamaktadır.
- **Grad-CAM:** Modelin karar verirken doğru şekilde pirinç tanelerine odaklandığı Grad-CAM analizi ile kanıtlanmıştır.


<img width="1001" height="470" alt="__results___19_0" src="https://github.com/user-attachments/assets/e327b0e6-9aa3-4759-b08c-181d7ae102d1" />


## 4. Sonuç ve Öğrendiklerim

Bu projeyi tamamlarken, bir derin öğrenme modelinin sadece kod yazmaktan ibaret olmadığını, aynı zamanda veri hazırlama, `EarlyStopping` gibi doğru teknikleri kullanarak eğitimi yönetme ve sonuçları `Grad-CAM` gibi araçlarla yorumlama gibi birçok adımdan oluştuğunu öğrendim. Geliştirdiğim modelin, pirinç türlerini **%99 gibi yüksek bir doğrulukla** ayırt edebilmesi, bu adımları doğru bir şekilde uyguladığımı gösteriyor.

Bu proje benim için harika bir başlangıç oldu ve gelecekte bu temelin üzerine eklemek istediğim birkaç fikrim var:

**Gelecekteki Adımlar İçin Fikirlerim:**
* **Farklı Modeller Denemek:** Bir sonraki adımda, `MobileNetV2` gibi hazır modellerle **Transfer Öğrenme (Transfer Learning)** tekniğini denemek ve sonuçları karşılaştırmak isterim.
* **Basit Bir Arayüz Oluşturmak:** Modelimin sadece notebook üzerinde kalması yerine, Streamlit gibi bir araçla, insanların kendi pirinç fotoğraflarını yükleyip sonucu görebilecekleri küçük bir web uygulaması yapmayı hedefleyebilirim.
* **Veri Setini Çeşitlendirmek:** Farklı açılardan çekilmiş resimler ekleyerek modelimin gerçek hayat koşullarında ne kadar başarılı olacağını test etmek ilginç bir deneyim olabilir.

Bu proje, bir fikri koda döküp somut bir sonuç elde etme konusunda bana büyük bir tecrübe ve motivasyon kazandırdı.

---

## 5. Kaggle Notebook

Projenin tüm kodlarını ve çıktılarını içeren Kaggle notebook'una aşağıdaki linkten ulaşabilirsiniz:

**[https://www.kaggle.com/code/emircanztrk/pirin-g-r-nt-s-n-fland-rmas-cnn-0-99]**
