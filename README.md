## Git & GitHub : Versiyon Kontrolü
- Git : Versiyon Kontrol Sistemidir.

### Windows Git Kurulum
Windows'a Git'i kurmak için [[kaynak]](https://git-scm.com/download/win).       <br/>
Hazır ayarlar kullanılarak `Next` butonuna tıklayıp geçiyoruz. En son `Install` seçeneğine tıklayarak yüklemeyi başlatıp yüklendikten sonra da `Finish` butonuna tıklayarak kapatıyoruz.
```bash
        git --version
```
Yükleme işlemi başarıyla sona erdikten sonra yukarıdaki komutu kullanarak Git versiyonunun kontrol edebiliriz.  <br/>
Komutları yükleme sonrası `Git Bash` komut iştemcisine yazıyoruz.
![](pictures/gitIm1.PNG)

### Mac ve Linux Kurulumu
Mac ve Linux sistemlerde hali hazırda Git kurulu olur.  <br/>
Eğer sistemde yüklü değilse ve yüklememiz gerekirse [[kaynak]](https://git-scm.com/download).   <br/>
Binary installer'ı kullanarak Git yüklenebilir.
```bash
        git --version
```

Yukarıdaki komutu kullanarak Git'in çalışıp çalışmadığını görebiliriz.
```bash
        git
```
Git yüklüyse yukarıdaki komutu girerek Git Dokümantasyonuna ulaşabiliriz.

###  Git Bash Terminal Kullanımı 
- İçerisinde bulunduğumuz dizinde diğer klasörleri ve dokümanları gösterir.
```bash
        ls      
```
![](pictures/ls.PNG)

- Klasör içerisindeki gizli dosyaları da görmek istersek:
```bash
        ls -la      
```
![](pictures/ls-la.PNG)

- Üzerinde bulunduğumuz dizini bulmak için:
```bash
        pwd
```
![](pictures/pwd.PNG)

- Dizindeki diğer klasörlere ulaşabilmek için:
```bash
        cd KlasorAdı
```
![](pictures/cd.PNG)

- Bir önceki dizine geri dönebilmek için:
```bash
        cd ..
```
![](pictures/cd...PNG)

- Terminal çıktılarını temizlemek için:
```bash
        clear
```

- Dizin üzerinde klasör oluşturmak için:
```bash
        mkdir KlasorAdı
```
![](pictures/mkdir.PNG)

- Dizinde dosya oluşturmak için:
 ```bash
        touch dosya.uzantısı
 ```
 ![](pictures/touch.PNG)

 - Dizinden dosya kaldırmak için:
```bash
        rm dosya.uzantısı
 ```
 ![](pictures/rm.PNG)

- Dizinden klasör kaldırmak için:
```bash
        rm -rf KlasorAdı
```
 ![](pictures/rm-rf.PNG)

### Kullanıcı Adı ve Email Girmek
- Git sistemine kullanıcı adımızı ve email bilgilerimizi kaydetmek için:
```bash
        git config --global user.name "UserName Surname"

        git config user.name
```
 ![](pictures/configUserName1.PNG)
 ![](pictures/configUserName2.PNG)

- Git sistemine email bilgisini kaydetmek için:
```bash
        git config --global user.email user@email.com

        git config user.email
```
 ![](pictures/configUserEmail.PNG)

### Git Temel Komutları
```cs
        Çalşıma Klasörü      =>      Index - Staging       =>       Local Repository
                          git add                      git commit
```

- Git güncel durumunu göstermek için:
```bash
        git status
```
Herhangi bir yerde `git init` komutunu çalıştırmadan önce git durumunu kontrol etmek her zaman için doğru olacaktır. <br/>
Aksi halde git'i birkaç farklı aktif etme durumu çakışmalara sebep olabilir.
 ![](pictures/gitstatus.PNG)

 - Git'i klasörde aktif etmek için:     master veya main branch olarak çalıştırır.
 ```bash
        git init
```
 ![](pictures/gitinit.PNG)

 - Git'e dosya veya klasör eklemek için:
```bash
        git add dosya.uzantısı
```
 ![](pictures/gitadd.PNG)

- Git'e yapılanların tümünü eklemek için:
```bash
        git add .
```
 ![](pictures/gitadd..PNG)

- Git'e eklenenlerin işlenebilmesi için:
```bash
        git commit -m "commit message"
```
- İşleme alma mesajı yapılanları açıklayıcı olmalıdır.
 ![](pictures/gitcommit.PNG)

 - İşlemleri görebilmek için:
 ```bash
        git log
```
Her commit'in kendine ait bir işlem numarası olur. <br/>
İşlem numarasına dönmek istersek o amaçla kullanılır.

        HEAD -> MASTER

Üzerinde bulunduğumun branch'ı gösterir
![](pictures/gitlog.PNG)

- Yapılan değişiklikleri tekrardan Git'e eklemek ve kontrolleri tekrardan sağlamak için kısaca:
```bash
        git add .
        git commit -m "commit message"
        git status
        git log
```
![](pictures/gitbref.PNG)

- Gizli kalmasını istediğimiz dosyaları `Local Repo`'ya kaydetmek istemeyiz.
- `git add` yapılmaması gerekir.
- Öncelikle `.gitignore` isimli bir dosya oluşturmalıyız.
```bash
        touch .gitignore
```
gitignore dosyası içerisine gizli kalmasını istediğimiz dosyayı uzantısıyla birlikte yazmalıyız.
Gizli kalmasını istediğimiz dosya artık Git sorumluluğuna girmez.
![](pictures/gitignore2.PNG)
![](pictures/gitignore1.PNG)

