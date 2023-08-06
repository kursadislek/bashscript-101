###Değişkenler
Değişkenler iki sınıfa ayrılır bunlar :

* System variables(sistem değişkenleri) ve 
* User variables(kullanıcı değişkenleri)

Sistem değişkenleri kullanıcı tarafından atanmayan, halihazırda sistem tarafından verilmiş olan değişkenlerdir.

Kullanıcı değişkenleri ise bizim tarafımızdan sonradan atanan değişkenlerdir. Bunlar script üzerinden verdiğimiz değişkenler veya kullanıcıdan veri girişi isteyerek aldığımız değişkenler olabilir.

Sistem değişkenlerine örnek vermek için bir script oluşturalım :
```shell
touch task3.sh
```
```shell
vi task3.sh             
```
Insert moda geçip alttaki komutları dosya içine kopyalayalım. 
```shell
#!/bin/bash
echo $BASH
echo $BASH_VERSION
whoami
date
echo $PWD
```
**Not1**   :   Büyük harflerle yazalım.
**Not2**   :   Komut ve değişkenlerin yazım şeklindeki farka dikkat edelim.
```shell
chmod +x task3.sh
```
Dosya uzantısı vermeden çalıştırabilmek için /bin altına ekleyelim.
```shell
mv task3.sh /bin
```
Komut dosyamızı çalıştıralım.
```shell
task3.sh
```

Son olarak neleri elde ettiğimizi görmek adına sisteme ait olan bu veri çıktılarını inceleyelim.

Yukarıdaki komutlara ek olarak sonradan verdiğimiz kullanıcı değişkenlerine (user variables) örnek oluşturalım. Aşadağıdaki komutları `vi` ile tekrar ekleyelim:
```shell
#!/bin/bash
echo $BASH
echo $BASH_VERSION
whoami
date
echo $PWD
isim=BulutBilişimciler
echo $isim
sayi1=25                #integer
echo $sayi1
```

`task3.sh`

Komut çıktısını inceleyelim.



Bash komut dosyalarında değişken adlandırması ve değer ataması yapılırken dikkat edilmesi gereken bazı kurallar bulunur. 
Değişken adlandırma kurallarını aşağıdaki şekilde özetleyebiliriz:

    1.  Değişken adları harf veya alt çizgi (_) ile başlamalıdır.
    2.  Değişken adları harf, sayı ve alt çizgi (_) içerebilir.
    3.  Değişken adları büyük/küçük harfe duyarlıdır. #case-sensitive
    4.  Değişken adları boşluk veya özel karakterler içermemelidir.
    5.  if, then, else, fi gibi sisteme ayrılmış anahtar sözcükler değişken adı olarak kullanılmamalıdır.

    Değişken adlandırma ve değişkene değer atama konusunda önemli hatırlatmalar :

        1.  Değişkenin kullanım amacını yansıtan anlamlı isimler kullanmak kodun anlaşır ve okunaklı    
            olması açısından önemlidir.
        2.  Değişken adlarında Türkçe karakterler kullanmamaya dikkat edelim.
        3.  Değişkene değer ataması yapılırken string veri tipi içeren değerleri çift tırnak "metin"
            içine alalım.


Değişken adlandırma ve değer atama örnekleri :
```shell
touch /bin/task4.sh
```
```shell
vi /bin/task4.sh
```
```shell
#!/bin/bash
adiniz=Linux_user
echo $adiniz

_KullaniciSayisi=99999
echo $_KullaniciSayisi

kullanici_adi=admin1
echo $kullanici_adi

turkce_karakterler="Türkçe karakterler ---> ğ, ü, ş, i, ö, ç kullanmamayagayret edelim."
echo $turkce_karakterler

echo ""

#Şimdide hatalı değişken adlandırması ve değer ataması yaptığımızda aldığımızhataları görelim

İlksayı=Birinciler
echo $İlksayı

Kullanici grubu="Öğrenciler"
echo $Kullanici grubu

users=Bütün kullanıcılar buradaya yazılacak
echo $users
```
```shell
chmod +x /bin/task4.sh
```
```shell
task4.sh
```