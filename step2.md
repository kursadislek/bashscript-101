###Terminoloji ve Tanımlar Hakkında Bilgiler

**Bash**
Açılımı "Bourne-Again Shell" olan Bash, Unix/Linux işletim sistemlerinde betik dili 
yorumlayıcısıdır. Sistem üzerinde varsayılan yorumlayıcı olması sebebiyle farkında olmadan sürekli kullanmaktayız.

Varsayılan betik dili yorumlayıcımızın hangisi olduğunu görüntüleyebilmek için aşağıdaki komutu çalıştıralım:
```shell
echo $SHELL
```

Alternatif olarak yorumlayıcının tam yolunu belirleyebilmek adına which komutunu da kullanabiliriz.
```shell
which bash
```


İki komutunda aynı sonucu verdiğini görelim.

Korn Shell, C Shell, Z Shell gibi Bash'den farklı yorumlayıcılarda olması sebebiyle kendi komutlarımızı yazarken scriptimiz içinde hangi kabuk yorumlayıcıyı kullanacağımızı belirlememiz gerekir.

Komut dosyamızın yorumlayıcısını Bash olarak tanımlamak için, yukarıdaki komutlar ile yürütülebilir dosyanın tam yolunu bulalım, önüne bir shebang yani #! ile betiğimizin ilk satırına ekleyelim.
```shell
#!/bin/bash
```

**Shell**
Kabuk olarak çevrilen shell, hem bir komut yorumlayıcısı hem de bir programlama dilidir. 
Shell etkileşimli veya etkileşimsiz komut yürütme izni veren bir makro işlemcisi olarak çalışır. Komutlarımızı,programlarımızı ve script'lerimizi çalıştırabileceğimiz bir ortamdır. Shell ya da diğer bir adıyla işletim sistemi kabukları komut satırı arabirimiyle(CLI) kullanılır. İşletim sisteminin etrafındaki en dış katman olduğu için kabuk olarak adlandırılır.

Birazdaha örneklendirerek açacak olursak şuan giriş yaptığımız bu platformda ekranımızda duran sanal makinamızda yürütülebilir komut dosylarını kullanarak sistemimizle etkileşim kurmamızı ve yönetmemizi sağlar.
Shell(kabuk), kullanıcılardan girdi isteyerek, girdilerini yorumlayarak ve ardından temel işletim sisteminin çıktısını işleyerek (bir okuma-değerlendirme-yazdırma döngüsü) kullanıcı-sistem etkileşimini yönetir.

Bazı linux komutlarını çalıştırmayı deneyerek shell'in çalışma mantığını anlayalım:

Hangi kullanıcı olarak oturum başlattığımızı görelim:
```shell
whoami
```


Ip adresimizi kontrol edelim:
```shell
hostname -i
```
Tarihi ve takvimi görüntüleyelim:
```shell
date
```
```shell
cal
```

Burada gerçekleştirdiğimiz uygulamadaki amaç, komutları ve kabuğu kullanarak, hangi kullanıcı olduğumuzu, ip adresini, geçerli tarih-saat ve takvim bilgilerini almak için işletim sistemimizle "etkileşim" kurmamızdı.



**Script**
Betik dili olarak da anlandırılan script'ler işletim sistemi üzerindeki yürütülebilir komut dosyalarını yazmak için kullanılan ve belirli bir sözdiminde yazılmış bir dizi talimatları içeren programlama dilidir.



**Uygulama Senaryosu:**
Yukarıda çalıştırdığımız komutlar gibi çok sayıda rutin kontrol-çalışma yaptığımızı ve bunların günlük görevler olarak gerçekleştirilerek hatasız uygulanması gerektiğini düşünelim. Tam bu noktada bütün komutları ve kontrol adımlarını birlikte yönetebilmek adına betik dilini kullanarak(bash script) shell etkileşimini otomatikleştirebiliriz. Yukarıdaki komutları tek bir komut gibi çalıştırmak için uygulama adımlarına geçelim :

Adım-1- Komut dosyamızı oluşturalım:
```shell
touch /task1.sh
```

Adım-2- Komut dosyamızı vi editör ile düzenlemek için açalım:
```shell
vi /task1.sh

```
Adım-3- Insert moda geçmek için " `i` " tuşuna basalım.

Adım-4- Aşağıdaki script'imizi task1.sh dosyasının içine yapıştıralım. (Boşluk bırakmadan)
```shell
#!/bin/bash
whoami
hostname -i
date
cal
```

Adım-5- " `ESC` " tuşuna basarak insert moddan çıkalım ve " `:wq` " ile dosyamızı kaydedip çıkalım.

Adım-6- /task1.sh dosyasını çalıştırabilmek için yürütütebilir hale getirelim:
```shell
chmod +x /task1.sh
```

Adım-7- Ayrı komutlar halinde çalıştırarak aldığımız çıktıyı, tek bir script ile görebileceğiz.  
```shell
/task1.sh
```

Bu bölümde eğitim içeriğinde sıkça kullancağımız terimlerin anlamını ve gerçek hayatta neleri ifade ettiğini öğrendik. Bunun yanında bazı temel linux komutlarını kullanarak ilk script'imizi uygulamış olduk.

