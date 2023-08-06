###While Döngüsü

While döngüsü belirli bir koşul üzerine haraket eder. Döngü içinde berlirlediğimiz koşul doğru olduğu sürece, `do` ile başlayan ve `done` ile biten bölüm arasındaki kodu yürütmeye devam eder.

```shell
while [ koşul ];
do
    komut
    durum
done
```
_Task25:_ Koşul sağlandığı sürece döngünün devam etmesi durumunu aşağıdaki çalışma ile örneklendirelim.

Komut dosyamızı oluşturup(crtask.sh) scriptimizi içine kopyalayalım.

```shell
crtask.sh
```
```shell
sayac=0
while [ $sayac -lt 4 ];
do
    let sayac+=1
    echo $sayac
done
```
Yazdığımız temel algoritma, sayacı 0'dan başlatarak herseferinde 1 arttırıp 4'den küçük olup olmadığı durumu sorgular. `sayac` değişkenine atanan sayı 4'den küçükse doğruluk koşulu devam eder ve `do` altında belirtiğimiz komutları uygular. Artarak devam eden sayac değişkeni 4'e eşit veya büyük olduğu ana gelince koşul doğruluğu bozulur ve `done` ile while döngüsü sonlanır.

_Task26:_ While döngüsü için örnek yapmaya devam edelim. Döngüyü kullanarak .txt dosyasındaki verileri çekelim.

Öncelikle örnek .txt dosyası oluşturalım.
```shell
touch /home/veriler.txt
```
```shell
vi /home/veriler.txt
```
```shell
Dersler         Alan        KullanıcıSayısı
BashScript      OS          100
Go              Programlama 50
Linux           OS          70
Python          Programlama 100
Pardus          OS          500
```

Sonra komut dosyamızı oluşturup içine komutlarımızı kopyalayalım.
```shell
crtask.sh
```
```shell
while read a b c 
do
    echo $b - $a
done < /home/veriler.txt
```
Buradaki komut dizinini incelediğimizde diğer döngülerden farklı olarak, koşulu satır sonuna geldiğinde döngünün sonlanacağı şekilde en sonda belirtik.

> Bölüm sonu.