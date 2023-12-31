# Git & GitHub : Versiyon Kontrolü
Git : Versiyon Kontrol Sistemidir.

### [Windows Git Kurulum](#)
Windows'a Git'i kurmak için [[kaynak]](https://git-scm.com/download/win).       <br/>
Hazır ayarlar kullanılarak `Next` butonuna tıklayıp geçebilirsiniz. En son `Install` seçeneğine tıklayarak yüklemeyi başlatıp yüklendikten sonra da `Finish` butonuna tıklayarak kapatabilirsiniz.
```bash
        git --version
```
Yükleme işlemi başarıyla sona erdikten sonra yukarıdaki komutu kullanarak Git versiyonunun kontrol edebilisiniz.  <br/>
Komutları yükleme sonrası `Git Bash` komut iştemcisine yazabilirsiniz.
![](pictures/gitIm1.PNG)

### [Mac ve Linux Kurulumu](#)
Mac ve Linux sistemlerde hali hazırda Git kurulu olur.  <br/>
Eğer sistemde yüklü değilse ve yüklemeniz gerekirse [[kaynak]](https://git-scm.com/download).   <br/>
Binary installer'ı kullanarak Git yüklenebilir.
```bash
        git --version 
```     

Yukarıdaki komutu kullanarak Git'in çalışıp çalışmadığını görebilirsiniz.
```bash
        git
```
Git yüklüyse yukarıdaki komutu girerek Git Dokümantasyonuna ulaşabilisiniz.

### [Git Bash - Terminal Kullanımı](#)
Windows, Mac ve Linux için Git komutları farklılık göstermez, aynıdır.

- İçerisinde bulunduğunuz dizinde diğer klasörleri ve dokümanları gösterir.

```bash
        ls      
```
![](pictures/ls.PNG)

- Klasör içerisindeki gizli dosyaları da görmek isterseniz:

```bash
        ls -la      
```
![](pictures/ls-la.PNG)

- Üzerinde bulunduğunuz dizini bulmak için:

```bash
        pwd
```
![](pictures/pwd.PNG)

- Dizindeki diğer klasörlere ulaşabilmek için:

```bash
        cd KlasorAdi
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
        mkdir KlasorAdi
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
        rm -rf KlasorAdi
```
 ![](pictures/rm-rf.PNG)

- Devam eden uzun bir liste karşınıza çıkarsa klavyeden `yön tuşlarıyla` aşağı veya yukarı haraket ettirebiliz.
- Listeden çıkmak için klavyeden `'q'` tuşuna basılması gerekir.

 ![](pictures/TerminalList.PNG)

### [Kullanıcı Adı ve Email Girmek](#)
- Git sistemine kullanıcı adınızı ve email bilgilerinizi kaydetmek için:

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

### [Git Temel Komutları](#)
```c
        Çalışma Klasörü      =>      Index - Staging       =>       Local Repository
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
İşlem numarasına dönmek isterseniz o amaçla kullanılır.

        HEAD -> master

Üzerinde bulunduğunuz branch'ı gösterir
![](pictures/gitlog.PNG)

- Yapılan değişiklikleri tekrardan Git'e eklemek ve kontrolleri tekrardan sağlamak için kısaca:

```bash
        git add .
        git commit -m "commit message"
        git status
        git log
```
![](pictures/gitbref.PNG)

Gizli kalmasını istediğimiz dosyaları `Local Repo`'ya kaydetmek istemeyiz.
- `git add` yapılmaması gerekir.
- Öncelikle `.gitignore` isimli bir dosya oluşturmalısınız.

```bash
        touch .gitignore
```
gitignore dosyası içerisine gizli kalmasını istediğiniz dosyayı uzantısıyla birlikte yazmalısınız.
Gizli kalmasını istediğiniz dosya artık Git sorumluluğuna girmez.
```c
        .gitignore  ==>  dosya.uzantısı
```
![](pictures/gitignore2.PNG)
![](pictures/gitignore1.PNG)

### [Branch İşlemleri](#)

        HEAD -> master

MASTER : Genellikle ana branch olarak kullanılır. Bir projenin bitmiş son halini temsil eder.
HEAD -> branch : Sizin git içerisinde hangi konumda (branch) olduğunuzu gösterir. Genellikle son commit'i gösterir.
- Var olan branch'leri görüntülemek için:

```bash
        git branch 
```
![](pictures/gitbranch.PNG)

- Başka bir branch oluşturmak için:

```bash
        git branch BranchAdi 
```
![](pictures/gitbranchN.PNG)

- Başka bir branch'a geçiş yapmak için:

```bash
        git switch BranchAdi 
```
![](pictures/gitswitch.PNG)

- İki branch'ı birleştirmek için:
Hangi branch'a merge'leyecekseniz o branch üzerinde olmalısınız.

```bash
        git branch master
        git merge BirlesirilecekBranch
```
```c
        master  <--  BirlesirilecekBranch
        master branchine BirlesirilecekBranch eklenmiş olur.
```
![](pictures/gitmerge.PNG)

### [Fast Forwarding](#)
 Master branch üzerinde hiçbir değişiklik yapmadan başka bir branch ile ilerleyerek en son Master branch ile birleştirme (merge) işlemidir.

![](pictures/gitfastforward.PNG)

### [Merge Conflict](#)
Master branch içerisinde commit oluşturarak Merge Conflict işlemini çözebilirsiniz.
![](pictures/gitconflict1.PNG)
![](pictures/gitconflict2.PNG)
![](pictures/gitconflict3.PNG)
![](pictures/gitconflict4.PNG)

### [Stash](#)
Başka bir branch'da oluşturulan bir dosya commit işlemi yapılmadan git'e eklendiyse (git add <>) ve ardından tekrar başka bir branch'e geçildiyse diğer branch'de oluşturulan dosya da geçilen branch'e taşınır.  <br/>
Bu durumu önlemek için kendi branch'iniz üzerindeki değişiklikleri saklayıp tutmanız gerekir. Bunun aşağıdaki kodu kullanabilirsiniz:

```bash
        git stash 
```
![](pictures/gitstash.PNG)

- Diğer branch üzerinde işlerinizi hallettikten sonra, kendi branch'inizde sakladığınız komutları aşağıdaki kod yardımıyla gerçekleştirebilrisiniz.

```bash
        git stash pop
```
![](pictures/gitstashpop.PNG)

- Saklanan verilerin listesini görebilmek için:

```bash
        git stash list
```
![](pictures/gitstashlist.PNG)

- İstediğiniz `Stash`'i işleme almak için:

```bash
        git stash apply stash@{i}
```
Stash'i tekrar uygulamaya alsak da gerektiğinde tekrar kullanabilmek adına yine saklanmaya devam eder.
![](pictures/gitstashapply.PNG)

- Var olan saklı Stash'lerin hepsini listeden temizlemek için:

```bash
        git stash clear
```
![](pictures/gitstashclear.PNG)

- Çalışma yaptığınız dosya, commit attıktan sonra bir şekilde bozulur veya sıkkıntı çıkartırsa ise eski commit'li haline döndürmek için aşağıdaki komutu kullanarak düzeltmenizi yapabilirsiniz:

```bash
        git restore dosya.uzantıs
```
![](pictures/gitrestore.PNG)

### [Checkout](#)
- Commitleriniz arasında gezinebilmek için:

```bash
        git checkout commitId
```
Detached HEAD : 
![](pictures/gitcheckout0.PNG)
![](pictures/gitcheckout1.PNG)
![](pictures/gitcheckout3.PNG)
![](pictures/gitcheckout2.PNG)

- Yapılacak işlemler yapıldıktan sonra ayrı bir branch oluşturulup devam edilebilir veya alınacak notlar vesayre alındıktan sonra  yapılabilecek en kolay haliyle çalışılan branch'a geri dönülebilir:

```bash
        git switch master
```
![](pictures/gitswitchmaster.PNG)

### [Reset ve Revert](#)
- Geçmiş bir `commit`'e dönüp ondan önceki bütün commit'leri kaldırmak için - commit'lerdeki değişiklikler silinmez:

```bash
        git reset donulecekCommitId
```
![](pictures/gitreset.PNG)

- Geçmiş bir `commit`'e dönüp ondan önceki bütün commit'leri ve yapılan işlemleri kaldırmak için:

```bash
        git reset --hard donulecekCommitId
```
![](pictures/gitresethard1.PNG)
![](pictures/gitresethard2.PNG)

- Geçmiş bir `commit`'e dönüp ondan önceki commit'leri silmeden yeni commit oluşturarak aynı branch üzerinden devam edebilmek için:

```bash
        git revert donulecekCommitId
```
![](pictures/gitrevert1.PNG)
![](pictures/gitrevert2.PNG)

İki dosya arasındaki değişiklikleri veya oluşan farklılıkları görebilmek için `git diff`komutunu kullanabilrsiniz.
- Son `commit` veya başka bir `commit` ile arasında ne gibi değişiklikler var bunları görebilmek için:

```bash
        git diff
```
![](pictures/gitdiff1.PNG)

```bash
        git diff commitId
```
![](pictures/gitdiff3.PNG)
![](pictures/gitdiff4.PNG)

- Üzerinde bulunduğunuz `branch` ile diğer `branch` arasında ne gibi değişiklikler var bunları görebilmek için:

```bash
        git diff BranchAdi
```
![](pictures/gitdiff2.PNG)

- İki farklı `branch` arasında ne gibi değişiklikler var bunları görebilmek için:

```bash
        git diff ilkBranchAdi ikinciBranchAdi 
```
![](pictures/gitdiff5.PNG)

- `git rebase` hem log temizlemek için hem de tarihi tekrar yazmak için kullanılabilir.
`master branch` içerisindeki değişiklikleri kendi branch'inize taşımak isterseniz de kullanabilirsiniz.
Fazladan `merge commit` işlemi yapılmamış olur ve loglar temizlenmiş ve sıralanmış olur.
!! `master branch` üzerinde başka bir ekip arkadaşınızın çalışıyor olmaması gerekir.  
!! Önemli olan `master` branch dışında başka bir branch'de bulunuyor olmaktır.
```bash
        git rebase master
```
![](pictures/gitrebase.PNG)

### [GitHub](#)
GitHub, sürüm kontrol sistemi olarak Git kullanan yazılım geliştirme projeleri için web tabanlı bir depolama servisidir. <br/>
Yaptığınız dokümantasyonları Git komutlarını kullanarak paylaşımlı bir şekilde sonradan ulaşabilmenizi sağlayarak depolanızı sağlar. <br/>
GitHub'a yüklemeden önce GitHub'da `Repositories > New` şeklinde veya arama çubuğu yanındaki `+` simgesine tıklayarak `New repository` seçeneğine tıklayarak yeni bir `Repository` oluşturmanız gerekir. Repo'nuza bir isim (Repository name*) ve isteğe bağlı olarak bir açıklama (Description (optional)) ekleyebilirsiniz. <br/>
Diğer kullanıcıların Repo'nuzu görmesini istiyorsanız `Public` seçeneği seçili olmalıdır. <br/>
Diğer kullanıcılar görmesin sadece ben görebileyim derseniz de `Private` seçeneğini seçebilirsiniz. <br/>

- GitHub'ınıza uzaktan bağlanmasını sağlamak için:
- `origin` içerisinde Repo'nun URL'ini tutar.

```bash
        git remote add origin https://github.com/UserName/GitRepoName.git
```
![](pictures/gitremote.PNG)

- Uzak Repo'nuza yapılanları gönderebilmek için:
!! Üzerinde bulunduğunuz branch `main branch` (ana branch'ınız hangisiyse o branch) olmalı ve o ana branch'ınızda işlemleri gerçekleştirmelisiziniz.
!! Bu işlemleri yapmadan önce GitHub hesabınızın Git üzerinden oturum açmış olması gerekir.
`-u`, `origin` ve `main`'a push edeceğini tutar.
```bash
        git push -u origin main

        git push origin main
        git push                        -> origin -> main
```
![](pictures/gitpush1.PNG)
![](pictures/gitpush2.PNG)
![](pictures/gitpush3.PNG)

- `Remote branch`'leri görüntülemek için:

```bash
        git branch -r
```
![](pictures/gitbranchR.PNG)
![](pictures/gitbranch-.PNG)

Pull Request : GitHub bize branch'lar arasında çakışma yok ise `merge` yapmanızı sağlayabilir. 
- GitHub'daki değişiklikleri kendi `Local Repo`'nuza taşımak için:

```bash
        git fetch origin BranchAdi
```

- Github'daki değişiklikleri eklemek ve ayrı bir branch oluşturmadan kendi branch'inizin üzerine değişiklikleri kaydetmek için:

        git pull = git fetch + git merge

```bash
        git pull 
```

- Başka birisinin GitHub'ındaki Repo'yu kendi Local Repo'nuza ekleyebilmek için:

```bash
        git clone https://github.com/AtakanTurgut/DataStructures_Advanced
```
![](pictures/gitclone.PNG)

- Fork işlemi yaparak diğer kullanıcıların Repo'sunu kendi hesabınıza Repo olarak ekleyebilirsiniz.
- Ardından kendi Repo'nuzdan `git clone` komutunu kullanarak kendi `Local Repo`'nuzda görebilisiniz.

Private bir Repo'ya geliştirici ekleyebilmek için:

        RepoName       ->      Collaborators        ->         Add people
---
## [Git Large File Storage (LFS)]()

Büyük dosyaları github'a göndermek için önce açık kaynaklı git eklentisini [Git LFS](https://git-lfs.com/) kurmanız gerekir.

Kurulum bittikten sonra repository dizinine geçilir ve aşağıdaki komut yardımıyla ilgili repo için büyük dosya takibi başlatılır.
```
git lfs install
```
Daha sonra hangi tür dosyaların "büyük dosya" olarak değerlendirileceğini belirtmek için aşağıdaki komut verillir. Bu örnekte `.gif` uzantılı dosyaları takip etmesini istedim.
```
git lfs track "*.gif"
```
Bu işlemden sonra oluşturduğunuz `.gitattributes` dosyasını repository'ye ekliyorsunuz.
```
git add .gitattributes
```
Artık dosyalarınızı repoya ekleyerek normal akışınıza devam edebilirsiniz.
