###For Döngüleri

For döngüsü, belirtilen listedeki herhangi bir sayıda sağlanan öğe için, verilen bir kodda yineleme yapmak için kullanılır. Bu sayade kullanmak istediğimiz komutları belirli bir sayıda çalıştırabiliriz.

**For Döngü Yapısı**

```shell
for değişken in öğeler;
do
    komut
done
```

Task21: For dögüsünün nasıl çalıştığını anlamak için temel bir örnek yapalım.

Komut dosyamızı oluşturup alttaki ifadeyi içine kopyalayalım.
```shell
for i in {0..5}
do
    echo $i
done
```

Komut çıktısında her i=1 , i=2 , i=3 , i=4 , i=5 değerleri için verilen öğe sayısınca döngü içinde i değişkenini yazdırmıştık olduk.

Task22: Yukarıdaki ifadeyi liste kullanmadan da for döngüsünde gerçekleştirebiliriz.
```shell
for (( i=0;i<=5;i++ ))
do
    echo $i
done

```

Task23: Dosya içindeki değerleri kullanarak öğeleri belirleyelim.

Home dizini altında deneme dosyası oluşturup içine başlıkları ekleyelim.
```shell
touch /home/deneme1.txt
```
```shell
vi /home/deneme1.txt
```
```shell
BulutBilişim
BashScript
ForDöngüsü
```

Daha sonra crtask.sh ile komut dosyamızı oluşturalım ve altaki söz dizimini ekleyelim.
```shell
for i in $( cat /home/deneme1.txt );
do
    echo $i
done
```

> Bölüm sonu.




