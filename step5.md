###Read ve Reply Kullanımı

Değişkenlere, script içinde statik bir atama yapmadan kullanıcıdan veri girdisi isteyerek de atamalar yapılabilir. Bu noktada kullanıcı veri girdisine bağlı olarak değişkene değer ataması yapmak için **read** ve **reply** kullanımını öğreneceğiz.

Komutları sırasıyla çalıştıralım.

Uygulama#1 :
```shell
touch /bin/task5.sh
```
```shell
vi /bin/task5.sh
```
```shell
#!/bin/bash
echo "Adınızı giriniz"
read isim1                      #Veri girişine bağlı olarak değişken belirledik.
echo "Kullanıcı adı $isim1"
```
```shell
chmod +x /bin/task5.sh
```
```shell
task5.sh
```

Uygulama#2 : Farklı sayılarda değişken ataması yapılabilir.
```shell
touch /bin/task6.sh
```
```shell
vi /bin/task6.sh
```
```shell
#!/bin/bash
echo "Kullanıcı adlarını tek satır olarak giriniz: "
read user1 user2 user3
echo "Kullanıcılar:$user1, $user2, $user3"
```
```shell
chmod +x /bin/task6.sh
```
```shell
task6.sh 
```

Uygulama#3 : **read -option** kullanımı :
```shell
touch /bin/task7.sh
```
```shell
vi /bin/task7.sh
```
```shell
#!/bin/bash
read -p "Kullanıcı adı: " ad
read -p "Mail adresiniz: " mail
echo "Adı: $ad"
echo "İletişim bilgisi: $mail"
```
```shell
chmod +x /bin/task7.sh
```
```shell
task7.sh
```

Uygulama#4 :
```shell
touch /bin/task8.sh
```
```shell
vi /bin/task8.sh
```
```shell
#!/bin/bash
read -p "Kullanıcı adı: " ad
read -sp "Şifreniz: " sifre
echo ""                             #Alt satıra geçmesi için boşluk yazdırdık.
echo "Adı: $ad"
echo "Kullanıcı şifresi: $sifre"
```
```shell
chmod +x /bin/task8.sh
```
```shell
task8.sh
```

Uygulama#5 : Kullanıcıdan alınan veriyi değişken oluşturmadan reply ile kullanımına bakalım.
```shell
touch /bin/task9.sh
```
```shell
vi /bin/task9.sh
```
```shell
#!/bin/bash
read -p "Kayıt olmak için mail adresinizi giriniz! : "
echo "Giriş yapmak için kullandığınız mail adresiniz : $REPLY"
```
```shell
chmod +x /bin/task9.sh
```
```shell
task9.sh
```


        