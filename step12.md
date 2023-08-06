###Fonksiyonlar
Linux işletim sistemlerinde, üzerinde tekrarlı bir şekilde aynı çözüm süreçlerini gerçekleştirdiğimiz benzer problem çözme formulleri kullanabiliriz. Fonksiyonlar Linux sistem yöneticisinin ya da bir programcının kodu düzenlemesine ve yeniden kullanmasına izin vererek, tüm betiğin verimliliğini, yürütme hızını ve okunabilirliğini artırır. Oluşturduğumuz fonksiyonları script içinde kullanarak komut tekrarının da önüne geçmiş oluruz.    

Fonksiyonlar özellikle, birden fazla sayıda komutu ya da belirlediğimiz algoritmayı ihtiyaç duymamız durumunda istediğimiz yerde kullanabilmemizi sağlar. Fonskiyonların tanımını özetleyecek olursak, belirli bir amaca yönelik komut dizisidir.

Fonksiyonların yapısı aşağıdaki şekildedir:

```shell
function fonksiyon_ismi () {
  komutlar
}
```
_Task27:_ Fonsiyon oluşturmaya başlangıç için bir örnek yapalım.

Komut dosyasını oluşturalım ve

```shell
crtask.sh
```
içine aşağıdaki fonksiyonu ekleyelim.
```shell
#!/bin/bash
function lokasyon () {
    pwd
    echo "pwd komutu suan hangi dizin icine konumlandıgınızı gosterir."
}
lokasyon
```
**Not:** Fonksiyonlar, aynı bir komut gibi kendi ismiyle kullanılır. Fonksiyonu kullanabilmek için kendi ismiyle çağırmalıyız. Bu nedenle parantez dışına ekledik.


_Task28:_ Sayının karesini alan bir fonksiyon oluşturalım.
Herzamanki gibi komut dosyamızı oluşturalım ve içine fonksiyonu ekleyelim:
```shell
crtask.sh
```
```shell
read -p "Karesi alincak sayiyi buraya giriniz = " n 
function sayinin_karesi () {
    sonuc=$(( $n**2 ))
    echo "Sonuc = $sonuc"
}
sayinin_karesi
```

_Task29:_ Fonksiyon içinde bir döngü kullanarak öğrendiğimiz farklı konuları birleştirelim.

Öncelikle örnek .txt dosyası oluşturalım.
```shell
touch /home/veriler2.txt
```
```shell
vi /home/veriler2.txt
```
Dosya içine aşağıdaki verileri ekleyelim:
```shell
Dersler         Alan        GoruntulenmeSayisi
BashScript      OS          100
Go              Programlama 50
Linux           OS          70
Python          Programlama 100
Pardus          OS          500
```
Kaydederek çıkış yapalım `:wq`
Daha sonra komut dosyamızı oluşturup içine komutlarımızı kopyalayalım.
```shell
crtask.sh
```
```shell
function oran () {
    while read a b c 
do
    echo $a - $c
done < /home/veriler2.txt 
}
oran
```

> Bölüm sonu.


