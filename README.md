<p align="center">
  <img src="https://cloud.githubusercontent.com/assets/2059754/24601246/753a7f36-1858-11e7-9d6b-7a0e64fb27f7.png" alt="bash logo"/>
</p>

## İçindekiler
  1. [Basit Komutlar](#1-basit-komutlar)  
    1.1. [Dosya Komutlar](#11-dosya-komutları)  
    1.2. [Text Komutları](#12-text-komutları)  
    1.3. [Dizin Komutları](#13-dizin-komutları)  
    1.4. [SSH, Sistem Bilgisi & Ağ Komutları](#14-ssh-sistem-bilgisi--ağ-komutları)  
    1.5. [İşlem İzleme Komutları](#15-İşlem-İzleme-komutları)
  2. [Basit Shell Programlama](#2-basit-shell-programlama)  
    2.1. [Değişkenler](#21-değişkenler)  
    2.2. [Diziler](#22-diziler)  
    2.3. [String Yerleştirme](#23-string-yerleştirme)  
    2.4. [Fonksiyonlar](#24-fonksiyonlar)  
    2.5. [Koşullar](#25-koşullar)  
    2.6. [Döngüler](#26-döngüler)  
  3. [İpuçları](#3-İpuçları)  
  4. [Hata Ayıklama - Debugging](#4--hata-ayıklama--debugging)  
  

# 1. Basit Komutlar

### a. `export`
Tüm çevre değişkenlerini göstermek için kullanılır. Özel bir çevre değişkeni özelliğini görüntülemek için, `echo $VARIABLE_NAME` kullanın. Alternatif olarak ayrıntılı görüntülemek için `printenv` komutu da kullanılabilir.
```bash
export
```
Örnek:
```bash
$ export
AWS_HOME=/Users/omergulen/.aws
LANG=en_US.UTF-8
LC_CTYPE=en_US.UTF-8
LESS=-R

$ echo $AWS_HOME
/Users/omergulen/.aws
```

### b. `whatis`
whatis kullanıcı komutları, sistem çağrıları, kütüphane fonksiyonları ve manuel sayfasındaki diğer şeylerin açıklamasını görüntüler.
```bash
whatis bir_sey
```
Örnek:
```bash
$ whatis bash
bash (1)             - GNU Bourne-Again SHell
```

### c. `whereis`
whereis çalıştırabilir dosyaları, kaynak kodlarını ve manuel sayfalarını sistem tarafından otomatik oluşturulan bir veri tabanı ile araştırır.
```bash
whereis isim
```
Örnek:
```bash
$ whereis php
/usr/bin/php
```

### d. `which`
which çalıştırabilir dosyaları belirtilmiş bir PATH (yol) içerisinde arar. Bu komut aranan çalıştırabilirlerin tam yolunu yazdırır.
```bash
which program_adi 
```
Örnek:
```bash
$ which php
/c/xampp/php/php
```

### e. `clear`
Pencere içeriğini temizler.

## 1.1. Dosya Komutları
<table>
   <tr>
      <td><a href="#a-cat">cat</a></td>
      <td><a href="#b-chmod">chmod</a></td>
      <td><a href="#c-chown">chown</a></td>
      <td><a href="#d-cp">cp</a></td>
      <td><a href="#e-diff">diff</a></td>
      <td><a href="#f-file">file</a></td>
      <td><a href="#g-find">find</a></td>
      <td><a href="#h-gunzip">gunzip</a></td>
      <td><a href="#i-gzcat">gzcat</a></td>
      <td><a href="#j-gzip">gzip</a></td>
      <td><a href="#k-head">head</a></td>
   </tr>
   <tr>
      <td><a href="#l-lpq">lpq</a></td>
      <td><a href="#m-lpr">lpr</a></td>
      <td><a href="#n-lprm">lprm</a></td>
      <td><a href="#o-ls">ls</a></td>
      <td><a href="#p-more">more</a></td>
      <td><a href="#q-mv">mv</a></td>
      <td><a href="#r-rm">rm</a></td>
      <td><a href="#s-tail">tail</a></td>
      <td><a href="#t-touch">touch</a></td>
   </tr>
</table>

### a. `cat`
UNIX veya Linux altında, aşağıdaki amaçlar için kullanılır.  
* Text dosyalarını ekranda gösterir
* Text dosyalarını kopyalar 
* Text dosyalarını birleştirir 
* Yeni text dosyaları oluşturur

Örnek:
```bash
cat dosya_adi
cat dosya1 dosya2 
cat dosya1 dosya2 > yeni_birlesmis_dosya
cat < dosya1 > dosya2 #dosya 1'i dosya2'ye kopyalar.
```

### b. `chmod`
```chmod``` komutu "change mode" yani mod değiştir anlamına karşılık gelmektedir ve dosyanın veya dizinin okunabilir, yazılabilir ve çalıştırabilir olmasını değiştirebilir. Daha fazla bilgi için bu [linki](https://ss64.com/bash/chmod.html) kontrol edin.
```bash
chmod -secenekler dosya_adi
chmod +x -w calistir_ama_yazama
```

### c. `chown`
chown komutu "change owner" yani sahibini değiştir anlamına karşılık gelmektedir ve verilen dosya veya dizinin sahibini kullanıcı ve grup olarak değiştirebilir. Basit kullanımı önce kullanıcı:grup adı gelir ve sonrasında dosya veya dizin adı verilir.
```bash
chown -secenekler kullanici:grop dosya_adi
```

### d. `cp`
Dosyaları kopyalar.  
```bash
cp dosya1 dosya2
cp /root/Desktop/file1.txt /var/www/html/file2.php
```
`dosya1` kaynak yolunu `dosya2` ise hedef yolunu belirtir.

### e. `diff`
Dosyaları karşılaştırıp, farklılıklarını gösterir. 
```bash
diff dosya1 dosya2
```

### f. `file`
Dosya türünü belirler.  
```bash
file dosya
```
Örnek:
```bash
$ file index.html
 index.html: HTML document, ASCII text
```
### g. `find`
Dizinde dosya arar.
```bash
find dizin secenek duzen(yapi)
```
Example:
```bash
$ find . -name README.md
$ find /home/ -name '*.png'
```

### h. `gunzip`
Dosyaları ```gzip``` ile çıkartır.  
```bash
gunzip dosya
```

### i. `gzcat`
Çıkarmadan gzip ile sıkıştırılmış dosyalara bakmamızı sağlar.  
```bash
gzcat dosya
```

### j. `gzip`
Dosyaları sıkıştırır. 
```bash
gzip dosya
```

### k. `head`
Dosyanın ilk 10 satırını yazdırır. 
```bash
head dosya
```

### l. `lpq`
Yazıcı baskı sırasını yazdırır.  
```bash
lpq
```
Örnek:
```bash
$ lpq
Sıra    Sahip       İş      Dosya(lar)                      Toplam Boyut
active  omergulen   59      deneme                          399360 bytes
1st     omergulen   60      (stdin)                         0 bytes
```

### m. `lpr`
Dosyayı yazıcıdan yazdırır.  
```bash
lpr dosya
```

### n. `lprm`
Yazıcı baskı sırasından bir iş siler.  
```bash
lprm is_numarasi
```

### o. `ls`
Dosyaları listelemek için kullanılır. Hiç bir yol veya dizin göstermezseniz bulunduğunuz dizinde çalışır. ```-l``` gibi listeleyip daha çok bilgi veren ve ```-a``` gibi tüm dosyaları (gizliler dahil) gösteren parametreleri vardır. Daha detaylı bilgi için [link](https://ss64.com/bash/ls.html).  
```bash
ls secenek
```
Örnek:
<pre>
$ ls -la
rwxr-xr-x   33 omergulen  staff    1122 Mar 27 18:44 .
drwxrwxrwx  60 omergulen  staff    2040 Mar 21 15:06 ..
-rw-r--r--@  1 omergulen  staff   14340 Mar 23 15:05 .DS_Store
-rw-r--r--   1 omergulen  staff     157 Mar 25 18:08 .bumpversion.cfg
-rw-r--r--   1 omergulen  staff    6515 Mar 25 18:08 .config.ini
-rw-r--r--   1 omergulen  staff    5805 Mar 27 18:44 .config.override.ini
drwxr-xr-x  17 omergulen  staff     578 Mar 27 23:36 .git
-rwxr-xr-x   1 omergulen  staff    2702 Mar 25 18:08 .gitignore
</pre>

### p. `more`
Dosyanın ilk kısmını gösterir (```Space``` ile hareket eder ve ```q``` ile çıkılır).  
```bash
more dosya
```

### q. `mv`
Dosyayı taşır.  
```bash
mv dosya1 dosya2
```
`dosya1` kaynak yolunu `dosya2` ise hedef yolunu belirtir.

Ayrıca dosyanın ismini değiştirmek için kullanır.
```bash
mv eski_isim yeni_isim
```

### r. `rm`
Dosyaları silmeye yarar. Bunu bir dizin üzerinde kullanmaya çalışmak hataya yol açar. `rm: directory: is a directory`
Dizin silmek için `-r` kullanmalısınız. Silinmeyen dosyaları zorla silmek için de `-f` komutu kullanılmaktadır.
```bash
rm dosya
```

#### DİKKAT: `rm -rf /` komutu tüm sistemin silinmesine yol açar, sanal makine dışında kullanılması tehlikelidir.

### s. `tail`
Outputs the last 10 lines of file. Use `-f` to output appended data as the file grows.  
Dosyanın son 10 satırını yazdırır. `-f` parametresiyle çıktıyı sona ekler dosya büyüdükçe.
```bash
tail dosya
```

### t. `touch`
Yetki ve zaman etiketini günceller. Böylelikle dosya var olmamışsa yaratır.
```bash
touch dosya
```
Örnek:
```bash
$ touch trick.md
```

## 1.2. Text Komutları

<table>
    <tr>
      <td><a href="#a-awk">awk</a></td>
      <td><a href="#b-cut">cut</a></td>
      <td><a href="#c-echo">echo</a></td>
      <td><a href="#d-egrep">egrep</a></td>
      <td><a href="#e-fgrep">fgrep</a></td>
      <td><a href="#f-fmt">fmt</a></td>
      <td><a href="#g-grep">grep</a></td>
      <td><a href="#h-nl">nl</a></td>
      <td><a href="#i-sed">sed</a></td>
      <td><a href="#j-sort">sort</a></td>
   </tr>
   <tr>
      <td><a href="#k-tr">tr</a></td>
      <td><a href="#l-uniq">uniq</a></td>
      <td><a href="#m-wc">wc</a></td>
   </tr>
</table>

### a. `awk`
awk text dosyalarını idare etmek için en iyi araçtır. Tüm dosyaları satır satır idare eder. Değiştirmezseniz normal olarak kelimeleri ayırmak için boşluğu kullanır. En yaygın kullanımı aşağıdaki gibidir:

```bash
awk '/arama_yapisi/ { eslesme_gerceklesirse_gerceklesecek_komut; }' parcalanacak_text_dosyasi
```

`/etc/passwd` dosyasını ele alalım. Dosyanın içeriği böyle oluyor normal şartlarda:
```
root:x:0:0:root:/root:/usr/bin/zsh
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
```
Şimdi sadece kullanıcı adlarını alalım buradan. `-F` parametresi neye göre ayıracağımızı gösterir. Burada `:` ayracımız oluyor. `{ print $1 }` komutu ilk karşılaştığı eşleşmeyi yazdırır.
```bash
awk -F':' '{ print $1 }' /etc/passwd
```
Komutu çalıştırdıktan sonra çıktı şöyle olacaktır.
```
root
daemon
bin
sys
sync
```
`awk` ' ı daha detaylı anlamak için, [link](https://www.cyberciti.biz/faq/bash-scripting-using-awk)'e göz atın.


### b. `cut`
Dosyanın her satırından seçilen kısımları siler veya gösterir.

*example.txt*
```bash
red riding hood went to the park to play
```

* boşlukla ayrı ve 2. , 7. , 9. elemanları göster*
```bash
cut -d " " -f2,7,9 ornek.txt
```
```bash
riding park play
```

### c. `echo`
Bir satır text yazdırır.

*"Hello World" yazdır*
```bash
echo Hello World
```
```bash
Hello World
```

*"Hello World" 'u kelimeleri arasında yeni satır koyarak yazdırır*
```bash
echo -ne "Hello\nWorld\n"
```
```bash
Hello
World
```

### d. `egrep`
Girdiğimiz yapı ile eşleşen satırları yazdır - Uzun yazımı ('grep -E' (extended))

*ornek.txt*
```bash
Lorem ipsum
dolor sit amet, 
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

*İçinde "Lorem" veya "dolor" geçen satırları yazdırır.*
```bash
egrep '(Lorem|dolor)' ornek.txt
ya da
grep -E '(Lorem|dolor)' ornek.txt
```
```bash
Lorem ipsum
dolor sit amet,
et dolore magna
duo dolores et ea
sanctus est Lorem
ipsum dolor sit
```

### e. `fgrep`
Girdiğiniz yapı ile tamamen eşleşen satırları yazdırır. ('grep -F' (fixed))

*ornek.txt*
```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
foo (Lorem|dolor) 
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

*'(Lorem|dolor)' un tam olarak geçtiği satırları yazdırır*
```bash
fgrep '(Lorem|dolor)' ornek.txt
ya da
grep -F '(Lorem|dolor)' ornek.txt
```
```bash
foo (Lorem|dolor) 
```

### f. `fmt`
Basit optimize text düzenleyici

*ornek: ornek.txt (1 satır)*
```bash
Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.
```

*ornek.txt dosyasının çıktısı 20 karakter genişliğinde olacak*
```bash
cat ornek.txt | fmt -w 20
```
```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

### g. `grep`
Text dosyalarının içine bakar. Dosya içerisinde arama yapmak için de kullanabilirsiniz.
```bash
grep yapi dosya
```
Örnek:
```bash
$ grep admin /etc/passwd
_kadmin_admin:*:218:-2:Kerberos Admin Service:/var/empty:/usr/bin/false
_kadmin_changepw:*:219:-2:Kerberos Change Password Service:/var/empty:/usr/bin/false
_krb_kadmin:*:231:-2:Open Directory Kerberos Admin Service:/var/empty:/usr/bin/false
```
Aramayı tersine çevirmek için `-i` parametresini, belirli bir dizin altındaki tüm text dosyalarını taramak için ise `-r`(recursive) parametresi kullanılabilir, örnek olarak:
```bash
$ grep -r admin /etc/
```
`-w` (word) parametresi de sadece kelimeleri aramak için kullanılaiblir. `grep` hakkında daha detaylı bilgi için: [link](https://www.cyberciti.biz/faq/grep-in-bash).

### h. `nl`
Dosyanın satırlarını numaralndırır

*ornek.txt*
```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

*ornek.txt'yi satır numaraları ile yazdır*
```bash
nl -s". " ornek.txt 
```
```bash
     1. Lorem ipsum
     2. dolor sit amet,
     3. consetetur
     4. sadipscing elitr,
     5. sed diam nonumy
     6. eirmod tempor
     7. invidunt ut labore
     8. et dolore magna
     9. aliquyam erat, sed
    10. diam voluptua. At
    11. vero eos et
    12. accusam et justo
    13. duo dolores et ea
    14. rebum. Stet clita
    15. kasd gubergren,
    16. no sea takimata
    17. sanctus est Lorem
    18. ipsum dolor sit
    19. amet.
```

### i. `sed`
Texti düzenlemek ve şekillendirmek için kullanılan bir editör

*ornek.txt*
```bash
Hello This is a Test 1 2 3 4
``` 

*tüm boşlukları tire(-) ile değiştir*
```bash
sed 's/ /-/g' ornek.txt
```
```bash
Hello-This-is-a-Test-1-2-3-4
```

*tüm rakamları "d" ile değiştir*
```bash
sed 's/[0-9]/d/g' ornek.txt
```
```bash
Hello This is a Test d d d d
```

### j. `sort`
Text dosyasının satırlarını alfabetik sıralar

*ornek.txt*
```bash
f
b
c
g
a
e
d
```

*sıralanmış ornek.txt*
```bash
sort ornek.txt
```
```bash
a
b
c
d
e
f
g
```

*rastgele sıralanmış ornek.txt*
```bash
sort ornek.txt | sort -R
```
```bash
b
f
a
c
d
g
e
```

### k. `tr`
Karakter silme veya değiştirme (translate)

*ornek.txt*
```bash
Hello World Foo Bar Baz!
```

*tüm küçük harfleri büyük harf yap*
```bash
cat ornek.txt | tr 'a-z' 'A-Z' 
```
```bash
HELLO WORLD FOO BAR BAZ!
```

*tüm boşlukları yeni satır yao*
```bash
cat ornek.txt | tr ' ' '\n'
```
```bash
Hello
World
Foo
Bar
Baz!
```

### l. `uniq`
Tekrar eden satırları sil ya da bildir

*ornek.txt*
```bash
a
a
b
a
b
c
d
c
```

*sadece eşsiz satırları göster(önce sıralamanız(sort) gerekir yoksa düzgün çalışmayacaktır*
```bash
sort ornek.txt | uniq
```
```bash
a
b
c
d
```

*farklı satırları birer kere göster ve aynı olanların kaçar kere geçtiğini yaz*
```bash
sort ornek.txt | uniq -c
```
```bash
    3 a
    2 b
    2 c
    1 d
```

### m. `wc`
Dosyada kaç satır, kelime ve karakter olduğunu yazar.  
```bash
wc dosya
```
Örnek:
```bash
$ wc ornek.txt
7459   15915  398400 ornek.txt
```
`7459` satır, `15915` kelime ve `398400` karakter içerir.

## 1.3. Dizin Komutları

<table>
   <tr>
      <td><a href="#a-cd">cd</a></td>
      <td><a href="#b-mkdir">mkdir</a></td>
      <td><a href="#c-pwd">pwd</a></td>
   </tr>
</table>

### a. `cd`
Sizi bir dizinden diğerine taşır(change directory). Aşağıdaki
```bash
$ cd
```
komutu sizi `home` dizinine taşır. Bu komut isteğe bağlı `dizin_adi` değişkeni alır ve sizi o dizine götürür.
```bash
cd dizin_adi
```

### b. `mkdir`
Yeni dizin oluşturur.  
```bash
mkdir dizin_adi
```

### c. `pwd`
Şu an hangi dizinde olduğunu yazdırır(print working directory).  
```bash
pwd
```

## 1.4. SSH, Sistem Bilgisi & Ağ Komutları

<table>
   <tr>
      <td><a href="#a-bg">bg</a></td>
      <td><a href="#b-cal">cal</a></td>
      <td><a href="#c-date">date</a></td>
      <td><a href="#d-df">df</a></td>
      <td><a href="#e-dig">dig</a></td>
      <td><a href="#f-du">du</a></td>
      <td><a href="#g-fg">fg</a></td>
      <td><a href="#h-finger">finger</a></td>      
      <td><a href="#i-last">last</a></td>
      <td><a href="#j-man">man</a></td>
   </tr>
   <tr>
      <td><a href="#k-passwd">passwd</a></td>
      <td><a href="#l-ping">ping</a></td>
      <td><a href="#m-ps">ps</a></td>
      <td><a href="#n-quota">quota</a></td>
      <td><a href="#o-scp">scp</a></td>
      <td><a href="#p-ssh">ssh</a></td>
      <td><a href="#q-top">top</a></td>
      <td><a href="#r-traceroute">traceroute</a></td>
      <td><a href="#s-uname">uname</a></td>
      <td><a href="#t-uptime">uptime</a></td>
      <td><a href="#u-w">w</a></td>
   </tr>
   <tr>
      <td><a href="#v-wget">wget</a></td>
      <td><a href="#w-whoami">whoami</a></td>
      <td><a href="#y-whois">whois</a></td>
   </tr>
</table>

### a. `bg`
Durdurulmuş veya arka plana atılmış işlemleri listeler, arka planda durdurulmuş bir işi devam ettirir.

### b. `cal`
Aylık takvimi gösterir.

### c. `date`
Anlık tarih ve saati gösterir.

### d. `df`
Disk kullanımını gösterir.

### e. `dig`
Domain'in DNS bilgilerini alır.  
```bash
dig domain
```

### f. `du`
Dosya ve dizinlerin disk kullanımını gösterir. Daha fazla bilgi için: [link](http://www.linfo.org/du.html)
```bash
du [secenek] [dosya|dizin]
```
Seçenekler:
- `-h` (human readable) Çıktıyı kilobyte (K), megabyte (M) ve gigabyte (G) olarak verir.
- `-s` (supress or summarize) dizinin toplam boyutunu yazar ve alt dizinler için rapor verir. 

Örnek:
```bash
du -sh resimler
1.4M resimler
```

### g. `fg`
Ön planda çalışan en son işlemi getirir veya arka planda çalışan işlemleri `jobs` komutu ile gördükten sonra ID numarası ile ön planda çalışmasını isteyebiliriz.

Örnek:
```bash
# jobs
[1]   Running                 bash download-file.sh &
[2]-  Running                 evolution &
[3]+  Done                    nautilus .

# fg %1
```

### h. `finger`
Kullanıcı hakkında bilgi verir.  
```bash
finger kullanici_adi
```

### i. `last`
Bahsedilen kullanıcının son girişini gösterir.  
```bash
last seninKullanici_adin
```

### j. `man`
Bir komutun dökümantasyonunu gösterir.  
```bash
man komut
```

Örnek:
```bash
man cd
man ls
```

### k. `passwd`
Belirtilen kullanıcı (belirtilmezse giriş yapmış kullanıcı) şifre belirlenmesini veya değiştirilmesini sağlar.
```bash
passwd [secenek] [kullanici]
```

Örnek:
```bash
passwd
sudo passwd jeff
```


### l. `ping`
Sunucuyu pingler ve sonucu yazdırır.  
```bash
ping sunucu_ip_or_domain
```

### m. `ps`
İşlemleri (processes) görüntüler.  
```bash
ps -u kullanici_adi
```

### n. `quota`
Disk kotanı gösterir.  
```bash
quota -v
```

### o. `scp`
Lokal sunucu ve uzak sunucu  veya iki uzak sunucu arasında dosya aktarımını sağlar.

*lokal sunucudan uzak sunucuya*
```bash
scp kaynak_dosya kullanici@sunucu:dizin/hedef_dosya
```
*uzak sunucudan lokal sunucuya*
```bash
scp kullanici@sunucu:dizin/kaynak_dosya hedef_dosya
scp -r kullanici@sunucu:dizin/kaynak_dizin hedef_dizin
```
Özel bir porta bağlanmak için `-P` parametresi kullanılabilir.  
```bash
scp -P port kullanici@sunucu:dizin/kaynak_dosya hedef_dosya
```

### p. `ssh`
ssh (SSH client) uzak makineye bağlanmak ve üzerinde komut çalıştırmak için tasarlanmış bir programdır.  
```bash
ssh kullanici@sunucu
```
Özel bir porta bağlanmak için `-P` parametresi kullanılabilir  
```bash
ssh -p port kullanici@sunucu
```

### q. `top`
Anlık aktif işlemleri görüntüler.

### r. `traceroute`
Bir ip paketinin (örnek olarak ping işlemini gerçeleştirirken kullandığımız ICMP paketi de olabilir) hedef adresine varana kadar hangi sunucu ve/veya yönlendiriciler üzerinden geçtiğini görmemize imkan sağlayan bir programdır.

Örnek:
```bash
traceroute 8.8.8.8
```

### s. `uname`
Kernel bilgisini gösterir.  
```bash
uname -a
```

### t. `uptime`
Sunucunun ne zamandır açık olduğunu gösterir.

### u. `w`
Sunucuda kimin online olduğunu gösterir.

### v. `wget`
Dosya indirir.  
```bash
wget dosya
wget http://site.com/dosya.txt
```

### w. `whoami`
Anlık giriş yapmış kullanıcı adını yazdırır.

### y. `whois`
Domain'in whois bilgilerini gösterir.  
```bash
whois domain
```

## 1.5. İşlem İzleme Komutları

<table>
   <tr>
      <td><a href="#a-kill">kill</a></td>
      <td><a href="#b-killall">killall</a></td>
      <td><a href="#c-&">&amp;</a></td>
      <td><a href="#d-nohup">nohup</a></td>
   </tr>
</table>

### a. `kill`
Verilen ID ile işlemleri sonlandırır.  
```bash
kill PID
```

### b. `killall`
Verilen isimdeki tüm işlemleri sonlandırır.  
```bash
killall islem_adi
```

### c. &
`&` simgesi verilen işlemin sonuna eklenir ve arka planda çalışacağını gösterir.
```bash
komut &
```

### d. `nohup`
"No Hang Up" sözüne karşılık gelen nohup komutu, "kapatma" anlamına gelir. Yani shell'den çıktığınızda dahi çalışmayı sürdürür.
```bash
nohup komut
```
`&` ile birlikte kullanarak arka plan işlemi oluşturulabilir
```bash
nohup komut &
```

# 2. Basit Shell Programlama


`shebang` bash programlamanın ilk satırına yazılan belirli text'e denir. Bu satır script'in tek başına sh, bash, python, php gibi programları yazmadan çalışabilmesini sağlar. 

```bash
#!/bin/bash
```

## 2.1. Değişkenler

bash üzerinde değişken yaratmak diğer dillerde olduğu gibidir. Veri tipleri yoktur. Bash içinde değişkenler sayı, karakter, karakter dizisi gibi şeyler alabilir. Başlangıçta tanımlarken ne olduğunu belirtmenize gerek yoktur, vermek istediğiniz değere eşitlemek yeterli olacaktır.

Örnek:
```bash
str="hello world"
```

Yukarıdaki satır `str`  adında bir değişken oluşturur ve "hello world" stringini atar. Değeri okumak için değişken isminin başına `$` koymak yeterlidir.

Örnek:
```bash
echo $str   # hello world
```
## 2.2. Diziler
Diğer diller gibi bash de dizilere sahiptir. Diziler birden çok değer içerek değişkenlerdir.Dizilerin değerleri için sayı sınırı yoktur. Bash'de ki dizler sıfır tabanlıdır. İlk eleman 0 ile belirtilir. Bir kaç dizi oluşturma yolu vardır, aşağıda gösterildiği gibi:

Örnekler:
```bash
dizi[0] = deger
dizi[1] = deger
dizi[2] = deger
dizi=([2]=deger [0]=deger [1]=deger)
dizi=(deger deger deger)
```
Bir dizinin özel bir değerini yazdırmak için:

```bash
${dizi[i]}     # belirteç "i" için
```

Hiç bir belirteç verilmezse, dizi 0'dan başlar. Dizide kaç değer olduğunu öğrenmek için aşağıdaki yazım kullanılır:

```bash
${#dizi[@]}
```

Bash ayrıca üçlü durumlara sahiptir. Aşağıdaki durumlara bakınız.

```bash
${degisken:-word}    # degisken varsa ve "null" değilse, degeri dondur; aksi halde "word" ü döndür
${degisken:=word}    # degisken varsa ve "null" değilse, degeri dondur; aksi halde "word" e eşitle ve değerini döndür
${degisken:+word}    # degisken varsa ve "null" değilse, "word" ü döndür; aksi halde "null" döndür
${degisken:offset:length}    # alt dizi ilerlemesi yapar. $degisken 'in alt dizilerini karakter uzunluğuna göre dallandırarak döndürür
```

## 2.3 String Yerleştirme

Stringleri düzenlemede bir kaç örneği inceleyelim

```bash
${degisken#deger}         # eğer verilen "deger" degisken'in değerinin başıyla eşleşiyorsa, eşleşen en kısa kısmı sil ve geri kalanı yazdır
${degisken##deger}        # eğer verilen "deger" degisken'in değerinin başıyla eşleşiyorsa, eşleşen en uzun kısmı sil ve geri kalanı yazdır
${degisken%deger}         # eğer verilen "deger" degisken'in değerinin sonuyla eşleşiyorsa, eşleşen en kısa kısmı sil ve geri kalanı yazdır
${degisken%%deger}        # eğer verilen "deger" degisken'in değerinin sonuyla eşleşiyorsa, eşleşen en uzun kısmı sil ve geri kalanı yazdır
${degisken/deger/yeni_deger}  # Değişkenin değeri içinde "deger" ile eşleşen en uzun kısım ile "yeni_deger" değiştirilir. Sadece ilk eşleşme değiştirilir
${degisken//deger/string} # Değişkenin değeri içinde "deger" ile eşleşen en uzun kısım ile "yeni_deger" değiştirilir. Tüm eşleşmeler değiştirilir
${#degisken_ismi}     # değişkenin değerinin uzunluğunu string olarak döndürür
```

## 2.4. Fonksiyonlar
Tüm programlama dillerinde olduğu gibi, bash'de de fonksiyonları birden fazla satır kodu tek seferde çalıştırmak ve tekrarlamak için kullanbiliriz. Fonksiyon tanımlamak `function my_func { my_code }` yazmak kadar kolay. Fonksiyon çağırmak da başka bir programı çağırmakla aynı şekilde sadece adını yazmanız yeterli.

```bash
functname() {
    shell commands
}
```

Örnek:
```bash
#!/bin/bash
function hello {
   echo world!
}
hello

function say {
    echo $1
}
say "hello world!"
```

Yukarıdaki kodu çalıştırdığımızda `hello` fonksiyonu "world!" yazdıracaktır. Yukarıdaki `hello` ve `say` fonksiyonları özdeştir. Tek farkları `say` fonksiyonu parametre alır ve aldığı ilk parametreyi `echo` komutu ile yazdırır. Argümanlar scripti çalıştırırkenki sırayla isimlendirilir. `1,2 ($1,$2)`

## 2.5. Koşullar

Bash'deki koşullar diğer programlama dilleri ile aynıdır.  `if` ifadesi doğru ise `then` durumu çalışır.
```bash
if [ifade]; then
    ifade doğru ise çalışacak durum
else
    ifade yanlış ise çalışacak durum
fi
```

Bazen iç içe if - else yazmak kafa karıştırıcı olabilir, bunun için `case statements` denilen (switch-case) yapıları bulunur.

```bash
case ifade in
    yapi1 )
        durum-komut ;;
    yapi2 )
        durum-komut ;;
    ...
esac
```

İfade Örnekleri:

```bash
durum1 && durum2  # iki durum da doğru olmalı
durum1 || durum2  # en az biri doğru olmalı

str1=str2       # str1 ve str2 eşittir
str1!=str2      # str1 ve str2 eşit değildir
str1<str2       # str1, str2'den azdır
str1>str2       # str1, str2'den çoktur
-n str1         # str1 "null" değildir (str1'in karakter uzunluğu 0'dan fazla)
-z str1         # str1 "null" dur (str1'in karakter uzunluğu 0)

-a dosya         # dosya var (oluşturulmuş)
-d dosya         # dosya var (oluşturulmuş) ve dosya bir dizin
-e dosya         # dosya var; -a ile aynı
-f dosya         # dosya var ve düzgün bir dosya (dizin veya özel dosya türü değil)
-r dosya         # okuma yetkin var
-s dosya         # dosya var ve boş değil
-w dosya         # yazma yatkin var
-x dosya         # dosya ve dizin üzerinde çalıştırma yetkin var, dizin ise çalıştırma yetkisi arar
-N dosya         # son okumadan beri dosya değiştirilmiş
-O dosya         # dosyanın sahibisin ( owner )
-G dosya         # dosya'nın group ID'si seninki ile eşleşiyor (birden çok grupta ise, grouplarından biri ile)

dosya1 -nt dosya2    # dosya1, dosya2'den daha yeni
dosya1 -ot dosya2    # dosya1, dosya2'den daha eski

-lt     # daha az (less than)
-le     # daha az veya eşit (less than or equal)
-eq     # eşit (equal)
-ge     # daha büyük veya eşit (greater than or equal)
-gt     # daha büyük (greater than)
-ne     # eşit değil (not equal)
```

## 2.6. Döngüler

Bash üzerinde üç tip döngü vardır. `for`, `while` ve `until`.

Farklı `for` Yazımı (Syntax):
```bash
for x := 1 to 10 do
begin
  durum - komutlar
end

for dongu_adi [in list]
do
  $name kullanan durum ve komutlar
done

for (( baslatma ; bitis_kosulu ; degisiklik ))
do
  durum ve komutlar...
done
```

`while` Yazımı (Syntax):
```bash
while kosullar; do
  durum ve komutlar
done
```

`until` Yazımı (Syntax):
```bash
until kosullar; do
  durum ve komutlar
done
```

# 3. İpuçları

## Alias (Takma ad) ekleme
`bash_profile` dosyasını `nano ~/.bash_profile` komutu ile veya `vim ~/.bash_profile` komutu ile açın
> alias dockerlogin='ssh www-data@omergulen.local -p2222'  # adınızı .bash_profile' e ekleyin

## Çabukça Özel Bir Dizine Gitme
`nano ~/.bashrc`
> export otel_kayitlari="/workspace/hotel-api/storage/logs"

```bash
source ~/.bashrc
cd $otel_kayitlari
```

## Yakalanmalardan Çıkış | Exit traps

Bash script'inizi daha düzenli, hatasız ve arkada gereksiz işlem bırakmayacak şekilde yazın.

```bash
function finish {
  # temizlemeyi yapın örn. açık kalan gereksiz işlemleri sonlandır
  jobs -p | xargs kill
}
trap finish EXIT
```

## Çevre değişkenlerinizi kaydedin

`export FOO = BAR` yaptığınızda, değişkenleriniz bu shell'de ve bunun üzerinden açılan shell'lerde etkili olacaktır. Kalıcılığı sağlamak için `~/.bash_profile` dosyasına aşağıdaki komutu ekleyin.

```bash
echo export FOO=BAR >> ~/.bash_profile
```

## Scriptlerinize erişim

Scriptlerinize kolayca erişmek için home klasörünüzün içinde `mkdir ~/bin` komutuyla `bin` dizini oluşturabilirsiniz, artık tüm scriptlerinizi bu dizine koyup erişebilirsiniz.

Eğer erişemezseniz, aşağıdaki kodu `~/.bash_profile`dosyanıza eklemeyi ve `source ~/.bash_profile` komutunu çalıştırmayı deneyin.
```bash
    # PATH değişkenini belirtin
    if [ -d "$HOME/bin" ] ; then
        PATH="$HOME/bin:$PATH"
    fi
```

# 4.  Hata Ayıklama | Debugging
`bash` komutuna farklı parametreler vererek kolayca scriptinizi derleyebilirsiniz. Örneğin `-n` parametresi kodu çalıştırmayıp sadece hata kontrolü yapacaktır, `-v` komutları çalıştırmadan yazdıracak, `-x` ise işlem bittikten sonra kodları yazdıracaktır.

```bash
bash -n script_adi
bash -v script_adi
bash -x script_adi
```

## Katkı Sağlama

- Sorunları bildir [How to](https://help.github.com/articles/creating-an-issue/)
- Geliştirmeler ile birlikte "pull request" açın [How to](https://help.github.com/articles/about-pull-requests/)
- Bilginin yayılmasına yardımcı olun.

## Lisans

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
