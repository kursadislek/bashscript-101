###Komut Dosyalarını Otomatize Edelim

Diğer alıştırmalara geçmeden önce, yaptığımız çalışmalarda komut dosyası oluşturma adımlarını sürekli olarak aynı şekilde uyguladığımızı farketmişsinizdir. Bash script eğitimindeki amaçlarımızdan birinin bash komutları kullanarak rutin işlerimizi otomatize etmek olduğuna deyinmiştik. Bash kullanımları için Giriş bölümünü tekrar okuyabilirsiniz.

Burada da komut dosyası oluşturma adımlarını otomatize ederek tek bir komut haline getirerek ilerleyelim. Böylelikle oluşturmak istediğimiz her .sh dosyasında manuel iş sayısını azaltmış olacağız.

Hatılatma amaçlı notlarımızı tekrar edelim :
-   vi editör ile açılan dosyada düzenleme yapmak için " `i` " tuşuna basarak insert moda geçebiliriz.
-   Insert mod çıkış için " `ESC` " .
-   Dosyadaki değişikleri kaydedip çıkmak için " `:wq` "
-   Herhangi bir yanlış edit yapmamız durumunda 
    yaptığımız değişiklikleri keydetmeden çıkmak istiyorsak " `:q!` "

Şimdi dosyamızı oluşturmak istediğimiz komutun adı crtask.sh olsun. Son bir kez manuel adımlarımızı uygulayarak dosyamızı oluşturalım :

Hatırlatma : Komut dosyaları /bin/ ve /sbin/ altında yer almaktadır.
```shell
touch /bin/crtask.sh
```
vi editör ile dosyayı açalım : 
```shell
vi /bin/crtask.sh
```

Aşağıdaki scriptimizi dosya içine kopyalayalım(Hepsini seçip sanal makinede açılan dosyada copy-paste yapmamız yeterli) :

```shell
#!/bin/bash
read -p 'Kaldığımız uygulama numarasını buraya girelim = ' n           
dosya=task$n.sh
touch /bin/$dosya
echo '#!/bin/bash' > /bin/$dosya
chmod +x /bin/$dosya
echo '#Komutlari buraya kopyalayabilirsiniz.' >> /bin/$dosya
echo 'Komut dosyasi olusturuldu'
which $dosya
sleep 2
vi /bin/$dosya
```

Dosyamızı yürütülebilir bir komut dosyası haline getirelim ve ardından çalıştıralım.
```shell
chmod +x /bin/crtask.sh
```
```shell
crtask.sh
```

Komutun /bin/ dizini altında oluştuğunu aşağıdaki komutu kullanarak doğrulayalım(oluşturduğumuz komutların hepsini burada görebiliriz):

```shell
ls -l /bin/ |grep task
```

Yaptığımız işlemlerin ne anlama geldiğini sırasıyla satır satır inceleyelim :

1)  İlk olarak herzamanki #!/bin/bash yolunu dosyamıza ekledik.
2)  read komutu ile klavyeden veri girişi istedik ve istediğimiz veriyi n değişkenine atadık.
3)  dosya değişkenine kalvyeden girdiğimiz n sayısını kullanarak yeni ismini taskn.sh olarak belirledik.
4)  dosya değişkenini yeni atadığımız adıyla /bin altında oluşturduk.
5)  Yeni komut dosyasına echo ile shebang idafesini ekledik.
6)  taskn.sh komut dosyasını yürütülebilir moda getirdik.
7)  Hatırlatma amaçlı yorum satırı ekledik.
8)  Adımların hatasız ilerlediğini de göstermek adına ekrana komut dosyasının oluşturulduğunu yazdırdık.
9)  Dosyanın, komut dosyası olduğunu doğrulamak adına which komutu ile sorgulama yaptık.
10) sleep komutunu kullanarak 3 sn bekleme süresi verdik. Böylelikle adımlarıda kaçırmamış olduk.
11) Dosyamızın kendiliğinden açılması için vi komutunu ekledik.

Böylelikle crtask.sh komutunu her çalıştırdığımızda bizim belirlediğimiz dosya numarası ile yeni task dosyamız oluşacak. Ayrıca dosya oluşturma adımlarında manuel süreçleri ve hataları azaltabiliriz. 

Daha sonraki adımlarda yazmak istediğimiz scripti insert modda açılan dosya içine eklemeliyiz. 


