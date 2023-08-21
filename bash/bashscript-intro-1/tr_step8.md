###Koşullu İfadelerde Uygulama Çalışmaları 

Uygulamalara geçmeden önce koşul durumları içeren if-else yapısını tekrar edelim :
```shell
if [ koşul ]
then
	durum
elif [ koşul ] 
then
	durum 
else
	do durum
fi
```




_Task15:_ Koşulların nasıl değerlendirildiğini anlamak adına temel bir uygulama yapalım.
Oluşturduğumuz crtask.sh ile yeni komut dosyamızı oluşturalım. Ardından aşağıdaki script'imizi dosya içine yapıştırıp komutu çalıştıralım.
```shell
crtask.sh
```
```shell
sayi1=10
sayi2=10

if [ $sayi1 -eq $sayi2 ]
then
        echo "Koşul doğrudur."
else
        echo "Koşul yanlıştır!"
fi
```

Daha önceki bölümlerde mantıksal 0 doğru ve mantıksal 1 sonucunun yanlış olduğuna değinmiştik. 
Koşullu durumlarda ve döngülerde koşul doğru ise bu durumu yap ; yanlış ise bu durumu yap şeklindeki yapıyı sıklıkla kullanacağız.

_Task16:_ Farklı sayıları birbiri ile kıyaslayalım.
```shell
crtask.sh
```
```shell
a=46
b=23

if [ $a -lt $b ]
then
        echo "a sayısı b sayısından küçüktür."
else
        echo "a sayısı b sayısından büyüktür."
fi
```

Buradaki if-else yapısında :
- eğer koşul doğru ise
  * ekrana " a sayısı b sayısından büyüktür " yaz
- koşul yanlış ise
    * ekrana " a sayısı b sayısından küçüktür " yaz

şeklinde temel bir uygulama gerçekleştirdik. Burdaki koşulları ve durumları ihtiyacımızı göre çoğaltabiliriz.


_Task17:_ Koşulları çoğaltarak if-else yapısında AND kıyaslamasını da kullanalım.
Yeni komut dosyamızı oluşturalım 
```shell
crtask.sh
```
ve içine aşağıdaki komutları yapıştıralım.
```shell
echo -n "İlk sayıyı girelim : "
read VAR1
echo -n "İkinci sayıyı girelim : "
read VAR2
echo -n "Üçüncü sayıyı girelim : "
read VAR3

if [[ $VAR1 -ge $VAR2 ]] && [[ $VAR1 -ge $VAR3 ]]
then
  echo "Girilen sayılar içinde $VAR1 sayısı en büyük sayıdır."
elif [[ $VAR2 -ge $VAR1 ]] && [[ $VAR2 -ge $VAR3 ]]
then
  echo "Girilen sayılar içinde $VAR2 sayısı en büyük sayıdır."
else
  echo "Girilen sayılar içinde $VAR3 ayısı en büyük sayıdır."
fi
```

_Task18:_ 
```shell
crtask.sh
```
```shell
password=admin
read -p ' Sifrenizi giriniz : ' input_password
if [ $password == $input_password ]
then
        echo "Sifre dogru"
else
        echo "Sifrenizi yanlis girdiniz."
fi
```
