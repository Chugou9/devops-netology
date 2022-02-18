# devops-netology
My repository for homework on devops course

##Это первое изменеие из домашнего задания

- **/.terraform/* Исключить любые папки, содержащие скрытую директорию .terraform и все что в ней содержится

- *.tfstate Исключить любые файлы с расширением .tfstate
- *.tfstate.* Исключить любые файлы с расширением .tfstate. и любым количеством символов после точки от расширения
- crash.log Исключить файлы crash.log отнисительно текущей директории gitingore файла
- *.tfvars Исключить любые файлы с расширением .tfvars
- ~~~ 
  override.tf  Исключить файлы из этого списка
  override.tf.json
  *_override.tf + с любым количеством символов из перед наименованием этих двух файлов
  *_override.tf.json
- 
  ~~~
    .terraformrc Исключить скрытый файл и 
    terraform.rc вот этот файл

# 2.4 Задание

##1.Найдите полный хеш и комментарий коммита, хеш которого начинается на aefea.
    hash - aefead2207ef7e2aa5dc81a34aedf0cad4c32545
  
    message - Update CHANGELOG.md
  
    achieved by - git show aefea
##2.Какому тегу соответствует коммит 85024d3?
    tag - 85024d310 (tag: v0.12.23)
    achieved by - git show --oneline 85024d3
##3.Сколько родителей у коммита b8d720? Напишите их хеши.
    achestors -  58dcac4b7 ffbcf5581
    2 предка так как merge commit
    achieved by - git show b8d720^
##4.Перечислите хеши и комментарии всех коммитов которые были сделаны между тегами v0.12.23 и v0.12.24.
- b14b74c49 [Website] vmc provider links
- 3f235065b Update CHANGELOG.md
- 6ae64e247 registry: Fix panic when server is unreachable
- 5c619ca1b website: Remove links to the getting started guide's old location
- 06275647e Update CHANGELOG.md
- d5f9411f5 command: Fix bug when using terraform login on Windows
- 4b6d06cc5 Update CHANGELOG.md
- dd01a3507 Update CHANGELOG.md
- 225466bc3 Cleanup after v0.12.23 release

    achived by -  git log  v0.12.23..v0.12.24 --oneline
##5.Найдите коммит в котором была создана функция func providerSource,</br> определение в коде выглядит так func providerSource(...) (вместо троеточего перечислены аргументы).
commit - 18dd1bb4d Mildwonkey/tfconfig upgrade (#23670)

diff --git a/command/init_test.go b/command/init_test.go </br>
--- a/command/init_test.go </br>
+++ b/command/init_test.go </br>
@@ -950,0 +950,50 @@ </br>
+func TestInit_providerSource(t *testing.T) {

    achived by - git grep providerSource // took file name and paste info another command
               - git log -L:providerSource:command/init_test.go
##6.Найдите все коммиты в которых была изменена функция globalPluginDirs.
- 78b122055       HEAD Remove config.go and update things using its aliases
- 52dbf9483       HEAD keep .terraform.d/plugins for discovery
- 41ab0aef7       HEAD Add missing OS_ARCH dir to global plugin paths
- 66ebff90c       HEAD move some more plugin search path logic to command
- 8364383c3       HEAD Push plugin discovery down into command package

       achieved by - git grep globalPluginDirs
                   - git log --oneline --source -L:globalPluginDirs:plugins.go --no-patch
##7. Кто автор функции synchronizedWriters?
Author: Martin Atkins <mart@degeneration.co.uk>

    achieved by -  git grep -n synchronizedWriters
                - git log -L:synchronizedWriters:synchronized_writers.go:
#3.1 Задание

##3
 - выбран Windows Terminal
 - Подправлена PS1 PS1='[\t] | j\j | ${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\n\$ '
   - Добавлено время
   - Текущие job в фоне
   - Ввод новых команд с новой строки
##5 Ресурсы VirtualBox по умолчанию
   - Оперативная память: 1024Mb
   - Процессоры: 2
   - Видеопамять: 4Mb
##6 Добавление ресурсов через vargrant-file
   ~~~
     config.vm.provider "virtualbox" do |v|
        v.name = 'devops_netology'
        v.memory = 1024
        v.cpus = 2
      end
  ~~~
##8 
  - Длина журнала history задается переменной HISTSIZE. Это описано на 863 строке мануала man bash.
  - ignoreboth - параметр переменной окружения HISTCONTROL, который позволяет
    не писать в историю команды, начинающиеся с одного или нескольких пробелов, и
    дублируемые команды.
##9 
  - {} используется в раскрытии скобок, также позволяет выполнить 
  указанные внутри команды группой в текущей оболочке
  - описано на 258 строчке в man bash и на 1092
##10
  - touch file{1..100000}
  - 300 тыс. не удалось создать из-за ошибки Argument list too long. (Превышен максимальный размер стэка)
##11
  - [[ -d /tmp ]] - возвращает true, если файл существует и является директорией
  - [[ -d /tmp ]] && echo 'Tmp is a directory'
##12
  ~~~
  mkdir /tmp/new_path_directory
  cp /bin/bash /tmp/new_path_directory
  PATH=/tmp/new_path_directory:$PATH
  type -a bash
  ~~~
##13
  - at - утилита, позволяющая планировать выполнение команд
  - batch == at -b - планирует выполнение команд только, если позволяет уровень загрузки системы. По умолчанию 1.5.
##14
  - exit 1
  - vagrant suspend

   