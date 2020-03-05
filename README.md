# Artificial Neural Networks and CNN

![Screenshot_2020-03-04_19-41-36](https://user-images.githubusercontent.com/54184905/76018028-a9334580-5f30-11ea-8364-350535da0b5d.png)
(Nöronun matamatiksel yapısı.)

L = X . W + B

X = input

W = Ağırlık

B = Bias

eğitim sonucu W ve B değerleri değişir.

ve bu L değerini aktivasyon fonksiyonundan geçiririz.

Y = sigmoid(L) şeklinde

![Screenshot_2020-03-04_19-47-40](https://user-images.githubusercontent.com/54184905/76018509-35de0380-5f31-11ea-8312-86354152398c.png)

![Screenshot_2020-03-04_19-51-08](https://user-images.githubusercontent.com/54184905/76018680-881f2480-5f31-11ea-946e-43716580461c.png)

(Resimde 2 rakamının yapay sinir ağlarından geçişi)

# Aktivasyon fonksiyonları

![Screenshot_2020-03-04_19-57-44](https://user-images.githubusercontent.com/54184905/76018888-e6e49e00-5f31-11ea-93d2-a1940b46e129.png)


1-) Sigmoid

* Sayıları [0,1] arasında sıkıştırır.
* Gradient ölümlü olabiliyor.
* 0 odaklı değil.
* exp() hesaplaması yapar ve yavaş çalışır.


2-) Tanh

* [-1,1] arasına sıkıştırır.
* Sıfır odaklı.
* Hayla gradient ölümlü olabiliyor.


3-) ReLu

* Negatifse 0, pozitifse olduğu gibi geçer.
* Gradient ölümü yok.
* Bilgisayarın hesaplaması daha kolay.
* Biyolojik nörona daha yakın.
* 0 odaklı değil.
* Bazı nöronlar ölebiliyor.


4-) Leaky Relu

* Relu 'nun getirdiği tüm avantajlar.
* 0 odaklı olduğu için nöron ölümü yok.


5-) Exponential Linear Unit (ELU)

* Leaky relu ile aynı avantaja sahip.
* exp() kullandığı için biraz daha yavaştır.


6-) Maxout

* Relu ve Leaky Relu 'yu genelleştiriyor.
* Nöron ölümü yok.
* Parametre sayısı iki katına çıkar.

# LOSS (Cost) Fonksiyonları

* Tahmin edilen değerin gerçek değerden ne kadar uzak olduğunu hesaplar.
* Eğitim esnasında zamanla sıfıra yaklaşmasını bekleriz.
* y_vals = tf.abs(tagret - x_vals)
* Tahmin ne kadar doğru diye matematiksel işlem yaparız.

![Screenshot_2020-03-04_21-00-56](https://user-images.githubusercontent.com/54184905/76020190-07adf300-5f34-11ea-8178-03dddef8b511.png)

# L2 Loss Fonksiyonları

![Screenshot_2020-03-04_21-05-23](https://user-images.githubusercontent.com/54184905/76020362-53609c80-5f34-11ea-87ab-355a19656dd6.png)

y = doğru olan değer

f(x) = tahmin

Hedeften ne kadar uzaklaşırsa o kadar fazla ceza veririz.

# Cross Entropy Loss Fonksiyonu

![Screenshot_2020-03-04_21-09-15](https://user-images.githubusercontent.com/54184905/76020590-c36f2280-5f34-11ea-8614-d0604e0aaac9.png)

Bilgi teorisinde, iki olasılık dağılımı arasındaki ve aynı temel olaylar kümesinin üzerindeki çapraz entropi, küme için kullanılan bir kodlama şeması tahmini bir olasılık dağılımı için optimize edilmişse kümeden çizilen bir olayı tanımlamak için gereken ortalama bit sayısını ölçer.

# Öğrenme Oranı (Learning Rate)

* Atacağımız adımları sembolize eder.
* Çok küçük bir sayı atanır (örn: 0,0005)
* Büyük olursa minumuma ulaşamaz.
* Küçük olursa model yavaş eğitilir.

![Screenshot_2020-03-05_21-48-46](https://user-images.githubusercontent.com/54184905/76021057-9d964d80-5f35-11ea-945b-89555a18a094.png)

# Gradient Descent

Minumum değere ulaşmak için uygulanan adım.

![Screenshot_2020-03-05_21-50-42](https://user-images.githubusercontent.com/54184905/76021209-e221e900-5f35-11ea-9eb7-9eed99c4e198.png)

![Screenshot_2020-03-05_21-51-44](https://user-images.githubusercontent.com/54184905/76021349-34630a00-5f36-11ea-9c8f-8081518e8b30.png)

(Karşılaştığımız hatalar)

# Back Propagation (Geri Besleme)

* Weight Bias değerlerini günceller.
* Her nöronun hataya ne kadar katkısı olduğunu hesaplamak için kullanırız.

![Screenshot_2020-03-05_23-12-17](https://user-images.githubusercontent.com/54184905/76021815-03cfa000-5f37-11ea-85bf-c0e9c5f8be75.png)

![Screenshot_2020-03-05_23-12-26](https://user-images.githubusercontent.com/54184905/76021828-07fbbd80-5f37-11ea-8248-778cdf119884.png)

![Screenshot_2020-03-05_23-12-45](https://user-images.githubusercontent.com/54184905/76021833-0b8f4480-5f37-11ea-9bda-588e98c4bf62.png)

# Overfitting

* Eğitilen modelin eğitim setini çok iyi öğrenip genelleştirme yapamamasına denir
* Underfitting ise tam tersi, modelin veriyi hiç öğrenememesidir.
* Algoritma ezber yapar, daha önce karşılaşmadığı bir veri görünce yanlış sonuçlar verir.

# Regularization

* Daha iyi genelleştirme yapılmasını sağlar

1-) Daha fazla data

Algoritmaya verdiğiniz veri sayısı ve verinin verimliliği size daha iyi sonuçlar verir.

2-) Data Augmentation

Verilerin üzerinde oynamalar yaparak (ters çevirme, büyültme küçültme gibi) yeni veri oluşturulur.

böylece az bir veriyi 2 katına çıkarta biliriz.

3-) Loss fonksiyonuna ekstra fonksiyon ekle

4-) Dropout

Bağzı nöronları sıfırlayarak, eğitimi eşit bir şekilde dağıtırız yani verileri bir kaç nörona odaklamayız.

![Screenshot_2020-03-05_22-05-10](https://user-images.githubusercontent.com/54184905/76022458-40e86200-5f38-11ea-814c-e5ced6058647.png)

# CNN (Konvolüsyonel Sinir Ağları)

* Resmi düzeltip vektör haline getirmeyiz, yani resmi üç boyutlu kullanırız.
* weight olarak küçük filitreler kullanacağız (örn: 3x3x3 bir filitre)
* Filitre resim üzerinde pixel pixel kayar.

![Screenshot_2020-03-05_22-09-38](https://user-images.githubusercontent.com/54184905/76022728-c10ec780-5f38-11ea-88f3-e2d2e4f1e60f.png)

* Output derinliği kaç tane filitre kullandıysak ona eşit olacak.
* ilk layerler basit olur sonraki layerler komplex olur.

![Screenshot_2020-03-05_22-10-39](https://user-images.githubusercontent.com/54184905/76022968-44301d80-5f39-11ea-9088-d0f09c04cb6a.png)

örnek (Konvolüsyonel Layer): 32x32x3 lük bir resmi 6*( 5x5x3 ) bir filitreden geçirirsek yeni oluşacak çıktı 24x24x6 bir resim olur.

* Stride = 2 olarak ayarlarsak filitre 1 pixel olarak kayacağına artık 2 pixel olarak kayar.
bu da çıktının boyutunu değiştirir.

* Boyutun küçülmesine engel olmak için kenar pixellere 0 ekleyerek resmi tekrardan büyütebiliriz.

# Poolin layer

* Parametre sayısını azaltmak için max pooling kullanırız.
* Her aktivasyon haritası için ayrı ayrı uygularız (Derinliği etkilemez.)
* Filitrelemedeki en büyük değeri alır.




