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
