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