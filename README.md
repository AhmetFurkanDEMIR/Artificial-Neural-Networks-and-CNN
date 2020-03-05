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




