###Case Yapısı
Bash scrip'deki case kullanımı C programlama dilindeki switch case yapısına benzer. Çok fazla sayıda koşul içeren durumlarda iç içe geçmiş if-else koşul durumlarını kullanmak yerine case yapısını kullanarak komutlarımızı sadeleştirebiliriz. 

Case yapsını aşağıdaki şekilde özetleyebiliriz :

```shell
case degisken in
  degisken_adi_1)
   durum
   ;;
 degisken_adi_2)
   durum
   ;;
 degisken_adi_N)
   durum
   ;;
 *)
   STATEMENTS
   ;;
esac
```

Case yapısındaki `degisken` ifadesi bir grup halinde bulunan diğer değişkenlerde aranır. Sonucun doğruluğuna göre ilgili durum yürütülür. Burada degisken verisini `degisken_adi_N` ifadesi ile karşılaştırıyoruz. Çift noktalı virgül " `;;` " her model için yürütülecek kod bloğunu ayırır. Yıldız işareti " `*` ", belirtilen kalıplardan hiçbiri ifadeyle eşleşmezse yürütülen varsayılan durumu temsil eder.


_Task19:_ Case yapısına temel bir örnek verelim.

Komut dosyamızı oluşturup 
```shell
crtask.sh
```
aşağıdaki örneği ekleyelim.
```shell
read -p 'Dizin adını buraya giriniz: ' dosya_dizini

case $dosya_dizini in
    "/")
        echo "Burası yetkili kullanıcı dizinidir."
        ;;
    "/home")
        echo "Kullanıcıya ait dosyalar burada bulunur."
        ;;
    "/tmp")
        echo "Burada sisteme ait geçici dosyalar bulunur."
        ;;
    *)
        echo "Farklı dizinleri görüntülemek için ls -la / komutunu kullanabilirsiniz."
        ;;
esac
```

_Task20:_ Bir önceki örneğe ek olarak `cd` komutu ile, değişkene girilen dizine konumlanalım ve `pwd` ile hangi dizinde olduğumuzu görelim.
```shell
crtask.sh
```
```shell
read -p 'Dizin adını buraya giriniz: ' dosya_dizini

case $dosya_dizini in
    "/")
        cd /
        echo "Burası yetkili kullanıcı dizinidir."
        pwd
        ;;
    "/home")
        cd /home
        echo "Kullanıcıya ait dosyalar burada bulunur."
        pwd
        ;;
    "/tmp")
        cd /tmp
        echo "Burada sisteme ait geçici dosyalar bulunur."
        pwd
        ;;
    *)
        echo "Farklı dizinleri görüntülemek için ls -la / komutunu kullanabilirsiniz."
        ls -la
        ;;
esac
```


