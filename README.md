# Репозиторий для **pull request**
* В своём аккаунте на GitHub создать копию репозитория **"AndreyBulgakov19/SCV_Git_PR"** с помощью кнопки **"Fork"**.
---
* Клонировать копию репозитория на локальный компьютер.
---
* Создать новую ветку.
---
* Добавить файл с инструкцией в новую ветку.
---
* Дополнить инструкцию разделами по работе с удалёнными репозиториями, pull request.
---
* Зафиксировать изменения (коммиты).
---
* Отправить изменения на GitHub.
---
* На сайте GitHub выполнить **Pull request**.
---


![Logo](Git_logo.png)
# Работа с Git GitHub
## 1. Проверка наличия установленного Git
В терминале выполнить команду `git version`.
Если Git установлен появиться сообщение с информацией о версии программы, иначе будет сообщение об ошибке.
## 2. Установка Git
Загружаем последнюю версию Git c cайта https://git-scm.com/downloads.
Устанавливаем с настройками по умолчанию.
## 3. Настройка Git
При первом использовании Git необходимо представиться. Для этого необходимо выполнить в терминале две команды:
```
git config --global user.name "Ваше имя английскими буквами"
git config --global user.email "ваша почта@example.com"
```
Данные не проверяются, можно указать любую почту и  любое имя. Но лучше написать реальные данные. Эти данные будут указываться, когда вы будете делать коммиты. Указание реальных данных упростит командную работу.
## 4. Инициализация репозитория
* Создаем папку на рабочем
столе. 
* Запускаем русифицированную
программу Visual Studio Code.
* Открываем созданную папку через проводник VS Code.

Для того, чтобы Git начал отслеживание изменений в файлах нужно эту папку инициализировать:

В терминале VS Code пишем команду:
```
git init
```
В папке создается скрытый файл - локальный репозиторий.

Чтобы  узнать статус происходящего пишем команду:
```
 git status
 ```

Git информирует в какой ветке мы находимся, есть ли неослеживаемые файлы. 
## 5. Запись изменений в репозиторий
Все изменения в файлах сохраняются на диск клавишами CTRL+S.

Для того, чтобы Git начал отслеживать изменения в файлах и контролировать версии их необходимо добавить, используя команду:
```
git add .\название файла
```
Писать полностью название файла не обязательно. Достаточно набрать две буквы и воспользоваться автозарполнением (клавиша Tab)

После добавления файла необходимо зафиксировать (сохранить) изменения с указанием коментария (что изменилось в данной версии) 

Для фиксации изменений пишем команду:
```
git commit -m ""
```

коментарии прописываем в кавычках.

Можно применять комбинированные команды, объединив команду `git add` и `git commit -m`:
```
git commit -a -m""` или `git commit -am""
```
## 6. Просмотр истории коммитов
Для просмотра количества сохраненных версий используют команду:

```
git log
``` 
Это жкрнал изменений событий, которые у нас хранятся

После запуска команды Git отобразит все коммиты, с коментариями. Каждому коммиту присваевается номер (индекс) по которому его можно найти.

Чтобы увидеть разницу между текущим файлом и сохраненным используется команда:
```
git diff
```
После запуска команды Git отображает все изменения: удаленную информацию со знаком "-", добавленную со знаком "+"

## 7. Перемещение между сохранениями
Для перемещения в другую версия сохранения необходимо воспользоваться командой: 
```
`git checkout №_коммита` 
```
Необязательно прописывать весь номер коммита, достаточно прописать первые четыре символа.
Чтобы вернуться в актуальную версию используют команду:
```
 git checkout master
 ```
## 8. Игнорирование файлов
Для того, чтобы исключить из отслеживания в репoзитории определенные файлы и папки необходимо создать там файл **.gitignore** и записать в него их названия или шаблоны, соответствующие таким файлам или папкам.

## 9. Создание веток в Git
Список веток в репозитории можно посмотреть с помощью команды:
```
git branch
```
Создать ветку можно командой:
```
git branch <название новой ветки>
```
По умолчанию имя основной ветки в Git -*master*
Для переключения между ветками используется команда:
```
git checkout <название ветки> 
```
Так же для создания ветки можно использовать команду:
```
git-checkout -b <название нового файла>
```
Эта команда создает и перемещает во вновь созданную ветку

## 10. Слияние веток и разрешения конфликтов
Если в новой ветке альтернативная информация вас устраивает и вы готовы ее залить в текущую ветку master, нужно убедиться, что мы находимся в нужной ветке, информация сохранена. Затем переходим в ветку master и запускаем команду:
```
git merge <название выбранной ветки>
```
Если все сделано верно, то в тексте появиться новая информация из слитой новой ветки.

Если один и тот же текст в разных ветках написан по - разному, при слиянии веток может произойти конфликт. Git не поймет какую версию нужно использовать. 
 В блоке будут отображаться два варианта: Heade и вариант, который пришел из ветки.

Для разрешения конфликта в редакторе VCCode есть возможность сделать выбор:
* принять текущую версию currend change
* принять входящую версию с новой ветки incomming change
* оставить оба варианта.

Нужно откорректировать выбранный вариант и сохранить.Затем добавить (add) и зафиксировать(commit -m"")

Когда ветка слита в чистовой вариант и уже не нужна, ее можно удалить командой:
```
git branch -d <название ветки>
```
## 11. Работа с изображениями
Находим картинку и размещаем этот файл в папку отслеживания. Открываем в редакторе VCCode.
Чтобы вставить изображения в текст достаточн написать:
```
 ![]()
 ```
 В квадратных скобках указать текст, который будет выводиться если изображение не загрузится. А в круглых скобках имя файла из которого необходимо изображение достать (его относительный путь).
  
В Git не принято добавлять фотографии или большие файлы.

Чтобы Git игнорировал файл с изображением и не отслеживал его, необходимо создать еще один файл с названием `.gitignore`. В файле прописать имя файла. Затем этот файл нужно закоммитить:
```
git add .gitignore
git commit -m""
```
# Работа с удаленными репозиториями
1. Создать аккаунт на GitHub
2. Создать локальный репозиторий
3. Создать удаленный репозиторий

Переходим в свой аккаунт на GitHub. В правом верхнем углу кнопка "+" в раскрывающемся списке выбираем "new repository". Окрывается станица "Create new repository". Добавляем название новому репозиторию, тип доступа публичный или приватный и нажимаем на кнопку "Creating repository"

4. Связать удаленный репозиторий с локальным
