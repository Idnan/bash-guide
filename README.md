<p align="center">
  <img src="https://cloud.githubusercontent.com/assets/2059754/24601246/753a7f36-1858-11e7-9d6b-7a0e64fb27f7.png" alt="bash logo"/>
</p>

## Содержание
  1. [Основные операции](#1-Основные-операции)  
    1.1. [Файловые операции](#11-Файловые-операции)  
    1.2. [Текстовые операции](#12-Текстовые-операции)  
    1.3. [Операции с каталогами](#13-Операции-с-каталогами)  
    1.4. [SSH, системная информация и сетевые операции](#14-SSH-системная-информация-и-сетевые-операции)  
    1.5. [Операции по мониторингу процессов](#15-Операции-по-мониторингу-процессов)
  2. [Основы программирования в командной строке](#2-Основы-программирования-в-командной-строке)  
    2.1. [Переменные](#21-Переменные)  
    2.2. [Массивы](#22-Массивы)  
    2.3. [Замена строк](#23-Замена-строк)  
    2.4. [Функции](#24-Функции)  
    2.5. [Условные выражения](#25-Условные-выражения)  
    2.6. [Циклы](#26-Циклы)  
  3. [Трюки](#3-Трюки)  
  4. [Отладка (Debug)](#4-Отладка-Debug)  
  

# 1. Основные операции

### a. `export`
Отображает все переменные среды. Если вы хотите получить подробную информацию о конкретной переменной, используйте `echo $VARIABLE_NAME`.  
```bash
export
```
Пример:
```bash
$ export
AWS_HOME=/Users/adnanadnan/.aws
LANG=en_US.UTF-8
LC_CTYPE=en_US.UTF-8
LESS=-R

$ echo $AWS_HOME
/Users/adnanadnan/.aws
```

### b. `whatis`
whatis показывает описание для пользовательских команд, системных вызовов, библиотечных функций и другое на страницах руководства.
```bash
whatis something
```
Пример:
```bash
$ whatis bash
bash (1)             - GNU Bourne-Again SHell
```

### c. `whereis`
whereis ищет исполняемые файлы, исходные файлы и страницы руководства, используя базу данных, созданную системой автоматически.
```bash
whereis name
```
Пример:
```bash
$ whereis php
/usr/bin/php
```

### d. `which`
which ищет исполняемые файлы в каталогах, заданных переменной среды PATH. Эта команда будет печатать полный путь к исполняемому файлу.
```bash
which program_name 
```
Пример:
```bash
$ which php
/c/xampp/php/php
```

### e. clear
Очищает содержимое окна.

## 1.1. Файловые операции
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
Может использоваться для следующих целей в UNIX или Linux.  
* Отображение текстовых файлов на экране
* Копирование текстовых файлов  
* Объединение текстовых файлов  
* Создание новых текстовых файлов  
```bash
cat filename
cat file1 file2 
cat file1 file2 > newcombinedfile
cat < file1 > file2 #copy file1 to file2
```

### b. `chmod`
Команда chmod позволяет вам изменять права на чтение, запись и выполнение для ваших файлов и папок. Для получения дополнительной информации об этой команде пройдите по [ссылке](https://ss64.com/bash/chmod.html).
```bash
chmod -options filename
```

### c. `chown`
Команда chown означает «владелец прав и позволяет вам изменять владельца данного файла или папки, которые могут быть пользователем и группой. Пользоваться просто, сначала пользователь (владелец), а затем группа, разделенная двоеточием.
```bash
chown -options user:group filename
```

### d. `cp`
Копирует файл из одного места в другое.  
```bash
cp filename1 filename2
```
Где `filename1` является исходным путем к файлу и `filename2` путь назначения к файлу.

### e. `diff`
Сравнивает файлы и перечисляет их различия.
```bash
diff filename1 filename2
```

### f. `file`
Определяет тип файла.
```bash
file filename
```
Пример:
```bash
$ file index.html
 index.html: HTML document, ASCII text
```
### g. `find`
Поиск файлов в каталоге.
```bash
find directory options pattern
```
Пример:
```bash
$ find . -name README.md
$ find /home/user1 -name '*.png'
```

### h. `gunzip`
Разархивирует файлы сжатые gzip.  
```bash
gunzip filename
```

### i. `gzcat`
Позволяет просматривать файлы архива gzipped без необходимости его разархивирования.
```bash
gzcat filename
```

### j. `gzip`
Архивирование файлов.  
```bash
gzip filename
```

### k. `head`
Выводит первые 10 строк файла 
```bash
head filename
```

### l. `lpq`
Проверка очереди вывода.
```bash
lpq
```
Пример:
```bash
$ lpq
Rank    Owner   Job     File(s)                         Total Size
active  adnanad 59      demo                            399360 bytes
1st     adnanad 60      (stdin)                         0 bytes
```

### m. `lpr`
Печать файла.  
```bash
lpr filename
```

### n. `lprm`
Удалить что-то из очереди печати.
```bash
lprm jobnumber
```

### o. `ls`
Список файлов. `ls` имеет множество опций: `-l` список файлов в 'длинном формате', который содержит точный размер файла, имя владельца файла, который имеет право просматривать его и время последнего изменения. `-a` список файлов, включая скрытые файлы. Для получения дополнительной информации об этой команде перейдите по [ссылке](https://ss64.com/bash/ls.html).  
```bash
ls option
```
Пример:
<pre>
$ ls -la
rwxr-xr-x   33 adnan  staff    1122 Mar 27 18:44 .
drwxrwxrwx  60 adnan  staff    2040 Mar 21 15:06 ..
-rw-r--r--@  1 adnan  staff   14340 Mar 23 15:05 .DS_Store
-rw-r--r--   1 adnan  staff     157 Mar 25 18:08 .bumpversion.cfg
-rw-r--r--   1 adnan  staff    6515 Mar 25 18:08 .config.ini
-rw-r--r--   1 adnan  staff    5805 Mar 27 18:44 .config.override.ini
drwxr-xr-x  17 adnan  staff     578 Mar 27 23:36 .git
-rwxr-xr-x   1 adnan  staff    2702 Mar 25 18:08 .gitignore
</pre>

### p. `more`
Показывает первую часть файла (перемещайтесь нажимая пробел и нажмите q для выхода).
```bash
more filename
```

### q. `mv`
Перемещает файл из одного места в другое.
```bash
mv filename1 filename2
```
Где `filename1` является исходным путем к файлу и `filename2` путь назначения к файлу.

Также может использоваться для переименования файла.
```bash
mv old_name new_name
```

### r. `rm`
Удаляет файл. Использование этой команды для каталога приводит к ошибке.
`rm: directory: is a directory`
Чтобы удалить каталог необходимо ввести `-r` который будет рекурсивно удалять содержимое каталога. При желании вы можете использовать `-f` флаг для принудительного удаления, то есть без каких-либо подтверждений и т.д.
```bash
rm filename
```

### s. `tail`
Выводит последние 10 строк файла. Используйте `-f` для вывода добавленных данных по мере роста файла.  
```bash
tail filename
```

### t. `touch`
Обновляет отметки времени создания и изменения файла. Если он не существует, он будет создан.
```bash
touch filename
```
Пример:
```bash
$ touch trick.md
```

## 1.2. Текстовые операции

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
awk является наиболее полезной командой для обработки текстовых файлов. Работает по строкам. По умолчанию для разделения полей используется пробел. Наиболее распространенным синтаксисом для команды awk является

```bash
awk '/search_pattern/ { action_to_take_if_pattern_matches; }' file_to_parse
```

Возьмем следующий файл `/etc/passwd`. Вот пример данных, которые содержит этот файл:
```
root:x:0:0:root:/root:/usr/bin/zsh
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
```
Итак, теперь вы можете получить только имя пользователя из этого файла. Где `-F` указывает на какой основе мы собираемся разделить поля. В нашем случае `:`. `{print $ 1}` означает вывод первого поля соответствия.
```bash
awk -F':' '{ print $1 }' /etc/passwd
```
После выполнения указанной команды вы получите следующий вывод.
```
root
daemon
bin
sys
sync
```
Подробнее о том, как использовать `awk`, перейдите по [ссылке](https://www.cyberciti.biz/faq/bash-scripting-using-awk).


### b. `cut`
Удалить разделы из каждой строки файлов.

*example.txt*
```bash
red riding hood went to the park to play
```

*покажите мне столбцы 2, 7 и 9 с пробелом в качестве разделителя*
```bash
cut -d " " -f2,7,9 example.txt
```
```bash
riding park play
```

### c. `echo`
Отображение строки текста

*отобразить «Hello World»*
```bash
echo Hello World
```
```bash
Hello World
```

*отобразите «Hello World» каждое слово с новой строки*
```bash
echo -ne "Hello\nWorld\n"
```
```bash
Hello
World
```

### d. `egrep`
Вывод строк, соответствующие шаблону - Extended Expression (псевдоним для: 'grep -E')

*example.txt*
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

*отобразить строки в которых есть «Lorem», либо «dolor».*
```bash
egrep '(Lorem|dolor)' example.txt
or
grep -E '(Lorem|dolor)' example.txt
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
Вывод строк, соответствующие шаблону - FIXED pattern matching (псевдоним для: 'grep -F')

*example.txt*
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

*Найти строку с '(Lorem|dolor)' в example.txt*
```bash
fgrep '(Lorem|dolor)' example.txt
or
grep -F '(Lorem|dolor)' example.txt
```
```bash
foo (Lorem|dolor) 
```

### f. `fmt`
Простое форматирование текста

*Пример: example.txt (1 строка)*
```bash
Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.
```

*выводить строки example.txt шириной 20 символов*
```bash
cat example.txt | fmt -w 20
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
Ищет текст внутри файлов. Вы можете использовать grep для поиска строк текста, которые соответствуют одному или нескольким регулярным выражениям, и выводит только соответствующие строки.  
```bash
grep pattern filename
```
Пример:
```bash
$ grep admin /etc/passwd
_kadmin_admin:*:218:-2:Kerberos Admin Service:/var/empty:/usr/bin/false
_kadmin_changepw:*:219:-2:Kerberos Change Password Service:/var/empty:/usr/bin/false
_krb_kadmin:*:231:-2:Open Directory Kerberos Admin Service:/var/empty:/usr/bin/false
```
Вы также можете игнорировать словосочетания с помощью опции `-i`. `-r` может использоваться для поиска всех файлов в указанном каталоге, пример:
```bash
$ grep -r admin /etc/
```
И `-w` для поиска только слов. Более подробно о `grep`, перейдите по [ссылке](https://www.cyberciti.biz/faq/grep-in-bash).

### h. `nl`
Номер строк в файле

*example.txt*
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

*вывести example.txt с номерами строк*
```bash
nl -s". " example.txt 
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
Потоковый редактор для фильтрации и преобразования текста.

*example.txt*
```bash
Hello This is a Test 1 2 3 4
``` 

*заменить все пробелы дефисом*
```bash
sed 's/ /-/g' example.txt
```
```bash
Hello-This-is-a-Test-1-2-3-4
```

*заменить все цифры на "d"*
```bash
sed 's/[0-9]/d/g' example.txt
```
```bash
Hello This is a Test d d d d
```

### j. `sort`
Сортирует строки в текстовом файле.

*example.txt*
```bash
f
b
c
g
a
e
d
```

*сортировать example.txt*
```bash
sort example.txt
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

*рандомизировать отсортированный example.txt*
```bash
sort example.txt | sort -R
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
Переводит или удаляет символы.

*example.txt*
```bash
Hello World Foo Bar Baz!
```

*заменяет все буквы нижнего регистра в верхний регистр*
```bash
cat example.txt | tr 'a-z' 'A-Z' 
```
```bash
HELLO WORLD FOO BAR BAZ!
```

*превращает все пробелы в новые строки*
```bash
cat example.txt | tr ' ' '\n'
```
```bash
Hello
World
Foo
Bar
Baz!
```

### l. `uniq`
Сообщает об повторяющиеся строках или пропускает их.

*example.txt*
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

*показавыет только уникальные строки example.txt (сначала нужно отсортировать его, иначе он не увидит совпадения)*
```bash
sort example.txt | uniq
```
```bash
a
b
c
d
```

*показавает уникальные элементы для каждой строки и сообщает, сколько экземпляров найдено*
```bash
sort example.txt | uniq -c
```
```bash
    3 a
    2 b
    2 c
    1 d
```

### m. `wc`
Сообщает, сколько строк, слов и символов содержит файл.
```bash
wc filename
```
Пример:
```bash
$ wc demo.txt
7459   15915  398400 demo.txt
```
Где `7459` линий, `15915` слов и `398400` символов.

## 1.3. Операции с каталогами

<table>
   <tr>
      <td><a href="#a-cd">cd</a></td>
      <td><a href="#b-mkdir">mkdir</a></td>
      <td><a href="#c-pwd">pwd</a></td>
   </tr>
</table>

### a. `cd`
Moves you from one directory to other. Running this  
```bash
$ cd
```
moves you to home directory. This command accepts an optional `dirname`, which moves you to that directory.
```bash
cd dirname
```

### b. `mkdir`
Makes a new directory.  
```bash
mkdir dirname
```

### c. `pwd`
Tells you which directory you currently are in.  
```bash
pwd
```

## 1.4. SSH, системная информация и сетевые операции

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
      <td><a href="#i-jobs">jobs</a></td>
      <td><a href="#j-last">last</a></td>
   </tr>
   <tr>
      <td><a href="#k-man">man</a></td>
      <td><a href="#l-passwd">passwd</a></td>
      <td><a href="#m-ping">ping</a></td>
      <td><a href="#n-ps">ps</a></td>
      <td><a href="#o-quota">quota</a></td>
      <td><a href="#p-scp">scp</a></td>
      <td><a href="#q-ssh">ssh</a></td>
      <td><a href="#r-top">top</a></td>
      <td><a href="#s-uname">uname</a></td>
      <td><a href="#t-uptime">uptime</a></td>
   </tr>
   <tr>
      <td><a href="#u-w">w</a></td>
      <td><a href="#v-wget">wget</a></td>
      <td><a href="#w-whoami">whoami</a></td>
      <td><a href="#x-whois">whois</a></td>
   </tr>
</table>

### a. `bg`
Список остановленных или фоновых заданий; возобновление работы в фоновом режиме.

### b. `cal`
Показывает календарь месяца.

### c. `date`
Показывает текущую дату и время.

### d. `df`
Показывает использование диска.

### e. `dig`
Получает информацию DNS для домена. 
```bash
dig domain
```

### f. `du`
Показывает дисковое использование файлов или каталогов. Для получения дополнительной информации об этой команде перейдите по этой [ссылке](http://www.linfo.org/du.html)
```bash
du [option] [filename|directory]
```
Опции:
- `-h` (человекочитаемое) Отображает вывод его в килобайтах (К), мегабайтах (М) и гигабайтах (G).
- `-s` (сжатое или общее) Выводит общее дисковое пространство каталога и отчеты для подкаталогов. 

Пример:
```bash
du -sh pictures
1.4M pictures
```

### g. `fg`
Команда возобновления работы задачи.

### h. `finger`
Отображает информацию о пользователе.  
```bash
finger username
```
### i. `jobs`
Список заданий, выполняемые в фоновом режиме, указывая номер задания.

### j. `last`
Список последних авторизаций указанного пользователя.
```bash
last yourUsername
```

### k. `man`
Показывает руководство для указанной команды.
```bash
man command
```

### l. `passwd`
Позволяет текущему зарегистрированному пользователю изменить свой пароль.

### m. `ping`
Запрашивает хост и выводит результаты.  
```bash
ping host
```

### n. `ps`
Перечисляет процессы.  
```bash
ps -u yourusername
```
Используйте флаг ef. e для каждого процесса и f для полного списка.
```bash
ps -ef
```

### o. `quota`
Показывает, какова ваша дисковая квота. 
```bash
quota -v
```

### p. `scp`
Передача файлов между локальным хостом и удаленным хостом или между двумя удаленными узлами.

*копирование с локального хоста на удаленный хост*
```bash
scp source_file user@host:directory/target_file
```
*копирование с удаленного хоста на локальный хост*
```bash
scp user@host:directory/source_file target_file
scp -r user@host:directory/source_folder target_folder
```
Эта команда также принимает опцию `-P`, которая может использоваться для подключения к определенному порту.  
```bash
scp -P port user@host:directory/source_file target_file
```

### q. `ssh`
ssh (SSH client) - это программа для входа в систему и выполнения команд на удаленном компьютере.  
```bash
ssh user@host
```
Эта команда также принимает опцию `-p`, которая может использоваться для подключения к определенному порту. 
```bash
ssh -p port user@host
```

### r. `top`
Отображает текущие активные процессы.

### s. `uname`
Показывает информацию о ядре. 
```bash
uname -a
```

### t. `uptime`
Показывает текущее время бесперебойной работы.

### u. `w`
Отображает, кто в сети.

### v. `wget`
Скачать файл.  
```bash
wget file
```

### w. `whoami`
Вернуть текущий логин.

### x. `whois`
Получает информацию whois для домена.
```bash
whois domain
```

## 1.5. Операции по мониторингу процессов

<table>
   <tr>
      <td><a href="#a-kill">kill</a></td>
      <td><a href="#b-killall">killall</a></td>
      <td><a href="#c-&">&amp;</a></td>
      <td><a href="#d-nohup">nohup</a></td>
   </tr>
</table>

### a. `kill`
Убивает (завершает) процессы с указанным идентификатором.
```bash
kill PID
```

### b. `killall`
Убейте все процессы по имени.
```bash
killall processname
```

### c. &
Символ `&` инструктирует команду работать как фоновый процесс в подоболочке.
```bash
command &
```

### d. `nohup`
nohup означает «No Hang Up (без зависаний)». Это позволяет запускать сценарий команд / процессов или оболочки, которые могут продолжаться в фоновом режиме после выхода из оболочки.
```bash
nohup command
```
Объедините его с `&` для создания фоновых процессов
```bash
nohup command &
```

# 2. Основы программирования в командной строке

Первая строка, которую вы напишете в файлах сценария bash, называется `shebang`. Эта строка в любом скрипте определяет способность скрипта быть выполненным как автономный исполняемый файл без ввода sh, bash, python, php и т. Д. Заранее в терминале.

```bash
#!/usr/bin/env bash
```

## 2.1. Переменные

Создание переменных в bash аналогично другим языкам. Нет типов данных. Переменная в bash может содержать число, символ, строку символов и т.д. Вам не нужно объявлять переменную. Просто присваивая значение она будет создана.

Пример:
```bash
str="hello world"
```

Вышеприведенная строка создает переменную `str` и присваивает ей «hello world». Значение переменной извлекается, помещая `$` в начало имени переменной.

Пример:
```bash
echo $str   # hello world
```
## 2.2. Массивы
Как и другие языки, bash также имеет массивы. Массив - это переменная, содержащая несколько значений. Максимального ограничения на размер массива нет. Массив в bash основан на нулевом значении. Первый элемент индексируется с элементом 0. Существует несколько способов создания массивов в bash. Ниже приведены примеры.

Примеры:
```bash
array[0] = val
array[1] = val
array[2] = val
array=([2]=val [0]=val [1]=val)
array=(val val val)
```
Чтобы отобразить значение в определенном индексе, используйте следующий синтаксис:

```bash
${array[i]}     # где i это индекс
```

Если индекс не указан, предполагается элемент массива 0. Чтобы узнать, сколько значений в массиве, используйте следующий синтаксис:

```bash
${#array[@]}
```

Bash также поддерживает тернарные условия. Ниже приведенны примеры.

```bash
${varname:-word}    # если varname существует и не значение не null, возвращается его значение; в ином случае вернется word
${varname:=word}    # если varname существует и не значение не null, возвращается его значение; в ином случае устанавливает word и после вернется его значение
${varname:+word}    # если varname существует и не значение не null, возвращается word; в ином случае вернется null
${varname:offset:length}    # выполняет расширение подстроки. Он возвращает подстроку $varname, начинающуюся со смещения(offset) и до символа длины(length)
```

## 2.3 Замена строк

Синтаксис как манипулировать строками

```bash
${variable#pattern}  # если шаблон соответствует началу значения переменной, удаляет самую короткую часть, которая соответствует и возвращает остальные
${variable##pattern}  # если шаблон соответствует началу значения переменной, удаляет самую длинную часть, которая соответствует и возвращает остальные
${variable%pattern}  # если шаблон соответствует концу значения переменной, удаляет самую короткую часть, которая соответствует и возвращает остальные
${variable%%pattern}  # если шаблон соответствует концу значения переменной, удаляет самую длинную часть, которая соответствует и возвращает остальные
${variable/pattern/string}  # самую длинная часть, соответствующая шаблону переменной, заменяется на строку. Заменяется только первое совпадение
${variable//pattern/string} # самую длинная часть, соответствующая шаблону переменной, заменяется на строку. Заменяются все совпадения
${#varname}  # возвращает длину значения переменной в виде символьной строки
```

## 2.4. Функции
Как и почти на любом языке программирования, вы можете использовать функции для группировки фрагментов кода более логичным способом или практиковать божественное искусство рекурсии. Объявление функции - это только вопрос написания функции my_func {my_code}. Вызов функции аналогичен вызову другой программы, вы просто пишете ее имя.

```bash
function name() {
    shell commands
}
```

Пример:
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

Когда вы запустите приведенный выше пример, функция `hello` выведет «world». Вышеупомянутые две функции «hello» и «say» идентичны. Основное различие - это функция `say`. Эта функция печатает первый аргумент, который он получает. Аргументы внутри функций обрабатываются так же, как аргументы, заданные скрипту.

## 2.5. Условные выражения

Условные выражения в bash аналогично другим языкам программирования. Условия имеют много форм, таких как самая простая форма: `if` и `then`, где оператор выполняется только в том случае, если выражение `if` истинно.

```bash
if [ выражение ]; then
    будет выполняться только в том случае, если выражение true
else
    будет выполняться, если выражение false
fi
```

Иногда, если условия сбивают с толка вы можете написать то же условие, используя `case statements`.

```bash
case expression in
    pattern1 )
        statements ;;
    pattern2 )
        statements ;;
    ...
esac
```

Примеры выражений:

```bash
statement1 && statement2  # оба утверждения верны
statement1 || statement2  # верно хотя бы одно из утверждений

str1=str2       # str1 соответствует str2
str1!=str2      # str1 не соответствует str2
str1<str2       # str1 меньше чем str2
str1>str2       # str1 больше чем str2
-n str1         # str1 не null (имеет длину больше 0)
-z str1         # str1 значение null (имеет длину 0)

-a file         # файл существует
-d file         # файл существует и является каталогом
-e file         # файл существует; то же самое -a
-f file         # файл существует и является обычным файлом (т. е. не каталогом или другим специальным типом файла)
-r file         # у вас есть права на чтение
-s file         # файл существует и не пуст
-w file         # у вас есть права на запись
-x file         # у вас есть права на выполнение для файла или права на поиск в каталоге, если оно является каталогом
-N file         # файл был изменен с момента последнего чтения
-O file         # вы владелец файлп
-G file         # идентификатор группы файлов совпадает с вашим (или одним из ваших, если вы находитесь в нескольких группах)

file1 -nt file2     # file1 новее чем file2
file1 -ot file2     # file1 старше чем file2

-lt     # меньше чем
-le     # меньше чем или равны
-eq     # равны
-ge     # больше чем или равны
-gt     # больше чем
-ne     # не равны
```

## 2.6. Циклы

Существует три типа циклов в bash. `for`,` while` и `until`.

Различные синтаксис `for`:
```bash
for x := 1 to 10 do
begin
  statements
end

for name [in list]
do
  statements that can use $name
done

for (( initialisation ; ending condition ; update ))
do
  statements...
done
```

`while` синтаксис:
```bash
while condition; do
  statements
done
```

`until` синтаксис:
```bash
until condition; do
  statements
done
```

# 3. Трюки

## Установить псевдоним
Откройте `bash_profile`, выполнив следующую команду` nano ~ / .bash_profile`
> alias dockerlogin='ssh www-data@adnan.local -p2222'  # добавьте свой псевдоним в
.bash_profile

## Чтобы быстро перейти к определенному каталогу
nano ~/.bashrc
> export hotellogs="/workspace/hotel-api/storage/logs"

```bash
source ~/.bashrc
cd $hotellogs
```

## Выйти из ловушки

Сделайте свои скрипты bash более надежными, выполнив очистку.

```bash
function finish {
  # ваша очистка здесь. например убить любые разветвленные процессы
  jobs -p | xargs kill
}
trap finish EXIT
```

## Сохранение переменных среды

Когда вы выполняете `export FOO = BAR`, ваша переменная экспортируется только в эту текущую оболочку и все ее дочерние элементы, чтобы в будущем вы могли просто добавить в свой файл `~/.bash_profile` команду для экспорта вашей переменной
```bash
echo export FOO=BAR >> ~/.bash_profile
```

## Доступ к вашим скриптам

Вы можете легко получить доступ к своим скриптам, создав папку bin в своем домашней директории с помощью `mkdir ~/bin`, теперь все скрипты, которые вы помещаете в эту папку, вы можете получить в любой директории.

Если вы не можете получить доступ, попробуйте добавить код ниже в файл `~/.bash_profile` и после запустите `source ~/.bash_profile`.
```bash
    # установите PATH, чтобы он включал в себя отдельный bin пользователя, если он существует
    if [ -d "$HOME/bin" ] ; then
        PATH="$HOME/bin:$PATH"
    fi
```

# 4. Отладка (Debug)
Вы можете легко отладить скрипт bash, передав разные опции команде `bash`. Например, `-n` не будет запускать команды и проверит только синтаксические ошибки. `-v` проверит перед выполнением. `-x` после выполнения командной строки.

```bash
bash -n scriptname
bash -v scriptname
bash -x scriptname
```

## Как помочь

- Сообщить об ошибке [Как?](https://help.github.com/articles/creating-an-issue/)
- Создать pull request с улучшениями [Как?](https://help.github.com/articles/about-pull-requests/)
- Поделиться

## Переводы
- [English ](https://github.com/itooww/bash-guide)
- [Chinese | 简体中文](https://github.com/vuuihc/bash-guide)
- [Turkish | Türkçe](https://github.com/omergulen/bash-guide)
- [Japanese | 日本語](https://github.com/itooww/bash-guide)
- [Russian | Русский](https://github.com/navinweb/bash-guide)

## License

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
