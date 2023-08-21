###Kıyaslama ve Koşul ifadeleri İfadeleri

Bu bölümde sayısal(numeric) ve dizi(string) ifadelerinin nasıl kıyaslandığını ve bu yapılarda nelerin kullanıldığını öğreneceğiz. Bu kıyaslama metotları ile tamsayıları,harfleri,kelimeleri ve cümleleri koşul içeren ifadeler biçiminde oluşturduğumuz komutlarda kullanabileceğiz.

Temel karşılaştırma operatörleri Türkçe ve İngilizce olarak aşağıdaki gibidir:

**Not:** Terimlerin, İngilizce tanımlarının kısaltması şeklinde olduğunu görmek aklımızda tutmamızı kolaylaştırabilir.

| İngilizce Açılımı | Shell Komut   | Sembol        | Türkçe Anlamı         |
| --                |:-------:      | :-----:       | :-----:               |
| less than         | -lt           | <             | küçük ise             |
| greater than      | -gt           | >             | büyük ise             |
| equal             | -eq           | =             | eşit ise              |
| not equal         | -ne           | !=            | eşit değil ise        |
| less or equal     | -le           | <=            | küçük veya eşit ise   |      
| greater or equal  | -ge           | >=            | büyük veya eşit ise   |   

_Task9:_ Sadece değişken atadığımız iki değeri kıyaslayalım ve doğru-yanlış sonuçlarının nasıl üretildiğine bakalım:
Sırasıyla komutlarımızı yazalım
```shell
x1=2
```
```shell
y1=3
```
Değerleri biribiri ile karşılaştıralım

```shell
[ $x1 -lt $y1 ]
```

Çıkan doğru ya da yanlış dönüş değerini görüntüleyelim
```shell
echo $?
```
---

**If-Else Kullanımı**

if-else yapısı, adından da anlaşılacağı üzere mantıksal olarak doğru ya da yanlış sonuçlar üreten koşul ifadeleridir. Script içine ekleyeceğimiz koşul değerine bağlı olarak iç içe geçmiş farklı şekillerde kullanılabilir.

Komut dosyasındaki söz dizimi aşağıdaki biçimdedir :

```shell
if [koşul];
then
    durum
elif [koşul]; then
    durum
else
    do durum
fi
```

**Koşul Durumlarında And(-a) , OR(-o) Kullanımı**

Farklı değişkenlerin birbiri ile kıyaslanması gereken durumlarda kullanabilceğimiz ifadelerdir.

Koşul1 AND Koşul2 gibi bir sözdiziminde , iki koşulunda doğru olup olmadığı kontrol edilir. İki koşulunda doğru olması durumunda sonuç 0 ; iki koşulun yanlış yada koşullardan birinin yanlış olması durumunda sonuç 0'dan farklı bir sayı üretir.

Koşul1 OR Koşul2 yapısında ise verilen iki koşuldan birinin doğru olması bütün durumun doğruluğu açısından yeterlidir. 

* **AND** ifadesi script içinde **-a** ile ;
* **OR** ifadesi script içinde **-o** ile gösterilir.

Şimdi bu açıklamaları örnekleyerek görelim.
_Task10:_
```shell
a=150
```
```shell
b=70
```
```shell
[ $a -gt 40 -a $b -lt 100 ]
```
```shell
echo $?
```

Şimdi buradaki satırları biraz inceleyelim :

* İlk iki satırda a ve b değişkinlerine integer değer atadık.
* [ a=150 değişkeni 40 sayısından büyükse ve(-a) b=70 değişkeni 100 sayısından küçükse ] şeklinde bir kıyaslama yaptık.
* Verilen koşulun mantıksal sonucu görüntülemek için `echo $?` kullandık. Bu ifadede koşul durumu oluşturuken AND yani -a kullandığımız için heriki durumun doğruluğu kontrol edildi. İki koşulda doğru olduğu için çıkan mantıksal sonuç 0 sayısı yani doğrudur.

**Not:** Bash script dilinde 0 mantıksal doğru ; 0'dan farklı sayılar mantıksal olarak yanlıştır.


_Task11:_ Mantıksal doğru ve yanlış konusu için bir örnek daha yapalım.
```shell
x1=2
```
```shell
y1=3
```
```shell
[ $x1 -lt $y1 ]
```
```shell
echo $?
```


Sonucu yazdırdığımızda yine 0 sayısını görüntüleyeceğiz. Yani 2 küçükse 3 koşulu doğrudur. 

_Task12:_
```shell
x2=1
```
```shell
y1=3
```
```shell
[ $x2 -ge $y1 ]
```
```shell
echo $?
```
Burda sonucu yazdırdığımızda çıkan sayının 0'dan farklı bir sayı olduğunu yani mantıksal olarak 
x2 büyük eşitse y1 koşulunun yanlış olduğunu görürüz.

**Önemli Hatırlatma :** Bash yazım kurallarında boşluk bir karakter olarak algılanır. Bu nedenle yazdığımız script'lerde nerelerde boşluk bıraktığımıza ve hangi kısımların boşluk olmadan yazıldığına dikkat edelim.

---

**Aritmatik İşlemler**

Temel matemetik işlemlerini bash script üzerinde alıştırmalarla görelim.

Hatırlatma : Boşluklara ve parantezlere dikkat edelim.

_Task13 :_
```shell
a=$((4+2))
```
```shell
b=$((4-2))
```
```shell
c=$((4*2))
```
```shell
d=$((4/2))
```
```shell
e=$((4**2))
```
```shell
f=$(( $a + $b ))
```
```shell
echo "a=$a , b=$b , c=$c , d=$d , e=$e , f=$f"
```

**expr command :** expr komutunu kullanmak, matematiksel ifademizi parantez veya tırnak içine almadan aritmetik işlemleri uygulamamızı sağlar.
```shell
expr 4 + 2
```
```shell
expr 4 * 2
```
```shell
expr 4 \* 2
```
```shell
expr 4 / 2
```
```shell
expr 4 - 2
```

**let command :** let komutu matematiksel bir ifadeyi değerlendirir ve sonucunu bir değişkende saklar.
```shell
let a=1+2
```
```shell
let b=2*($a-1)
```
```shell
let c=($b**3)/2
```
```shell
echo "a=$a , b=$b , c=$c"
```

**bc command :** Ondalık sayılarla ya da virgül içeren sayılarla çalışmak istersek bc komutunu kullanabiliriz.
```shell
echo "6.5 / 3.3" | bc
```
```shell
echo "scale=2;6.5 / 3.3" | bc
```
```shell
sonuc=$( echo "scale=50;sqrt(50)" | bc )
```
```shell
echo $sonuc
```
