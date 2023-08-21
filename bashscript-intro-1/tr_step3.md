###Komut Dosyaları

Oturum başlatıldığında Shell komut satırı varsayılanda **" $ "** işareti olan shell prompt ile kullanıcıdan komut girişi bekler. Mevcut kullanıcı bizim oturum açtığımız sistemindeki gibi root kullancısı ise prompt **" # "** işareti şeklinde görünür.

Linux ve dağıtımı işletim sistemlerinde komut sözdizimi(syntax) aşağıdaki şekildedir :
```shell
command [OPTIONS] arguments
```

Bu söz dizimine örnek olması açısından aşağıdaki komut ile root dizini altındaki dizinleri uzun liste formatında zamana göre en yeni dosya altta olacak şekilde listeleyelim:
```shell
ls -lrt /
```

Buradaki amacımız komut, seçenek ve etkilenen argüman şeklinde syntax'ı anlamak.

Bash betiklerini anlamak için bazı denemeler gerçekleştirelim.

Bir metin dizisi veya bir değişkenin değerini yazdırmak için echo komutunu kullanalım:
```shell
echo "Bash Script Giriş Dersleri"
```
---
**Bash Betikleri Oluşturma ve Çalıştırma**

Bir önceki bölümde task1.sh komutunda olduğu gibi bash script dosyaları **.sh** ile biter. 

Uygulama adımları :

_Adım-1-_ Kendi komut dosyamızı oluşturalım:
**Not:** Her zaman root(/) altında değil istenilen farklı bir dizin altında da oluşturabiliriz.
```shell
mkdir -p /home/BashScript_Dersleri/         #Belirlediğimiz başlıkta dizin oluşturduk.
```
```shell
touch /home/BashScript_Dersleri/task2.sh    #Dizin altında komut dosyamızı oluşturduk.
```

_Adım-2-_ vi text editör ile dosyamızı düzenlemek için açalım.
```shell
vi /home/BashScript_Dersleri/task2.sh       
```

_Adım-3-_ Alttaki script'i dosyamızın içine ekleyelim.

```shell
#!/bin/bash
message="Merhaba, Bulut Bilişmciler Bash Script Derslerine Hoş Geldin..."
echo $message
echo "Şuan tarih $(date)"
echo "date komutunda takıldığın yerlerde " date --help " şeklinde komutdetaylarına ulaşabilirsin"
#Hatırlatma: Yorum satırları herhangi bir değer yada komut olarak algılanmamaktadır.
#Yorum1
#Yorum2
```

_Adım-4-_ Yürütme yetkileri:
```shell
chmod +x /home/BashScript_Dersleri/task2.sh
```

_Adım-5-_ Komut dosyamızın diğer dosyalarla farkını görmek için dosya tipini görüntüleyelim:
```shell
file /home/BashScript_Dersleri/task2.sh
```

_Adım-6-_ Komut dosyamızı sistemimiz üzerinde çalıştıralım.
```shell
/home/BashScript_Dersleri/task2.sh
```

Çıktılarımızı görüntüledikten sonra Bash Script senaryomuzu satır satır inceleyelim:

Satır#1 :   Shebang olarak adlandıran **#!/bin/bash** ifadesi, bash kabuğu yolunu işaret eder.
İşletim sistemine bash script kullanacağımızı söylemiş olduk. 

Satır#2 :   message değişkenine string bir ifade atandı.
**Not:** Değişken isimlerinde sorun yaşamamak adına Türkçe karakter kullanmamayı öneririz.

Satır#3 :   Geçerli tarih ekrana yazdırıldı.

Satır#4 :   Aynı şekilde belirlediğimiz cümle ekrana yazdırıldı.

---
**Bash Script Yorum Satırı**

Bask script dosyalarında yorum satırları **" # "** ile başlar. Bu ifade, # ile başlayan herhangi bir satırın yorum olduğunu söyleyer ve bash yorumlayıcısı tarafından değerlendirmeye alınmaz.

Yorum satırları script'lerin dokümante edilmesine ve yazdığımız notlar ile başkalarının kodu anlamsına yardımcı olur. 

Script'ler içinde kullanılar yorum satırlarına örnek verelim :

```shell
#!/bin/bash
message="Merhaba, Bulut Bilişmciler Bash Script Derslerine Hoş Geldin..."
echo $message
echo "Şuan tarih $(date)"
echo "date komutunda takıldığın yerlerde " date --help " şeklinde komut detaylarına ulaşabilirsin"
#Hatırlatma: Yorum satırları herhangi bir değer yada komut olarak algılanmamaktadır.
#Yorum1
#Yorum2
```

