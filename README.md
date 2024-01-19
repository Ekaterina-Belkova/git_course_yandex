# Шпаргалка. Базовые команды в консоли Git

## Навигация


* pwd (от англ. print working directory, «показать рабочую папку») — покажи, в какой я папке;
* ls (от англ. list directory contents, «отобразить содержимое директории») — покажи файлы и папки в текущей папке;
* ls -a — покажи также скрытые файлы и папки, названия которых начинаются с символа .;
* cd first-project (от англ. change directory, «сменить директорию») — перейди в папку first-project;
* cd first-project/html — перейди в папку html, которая находится в папке first-project;
* cd .. — перейди на уровень выше, в родительскую папку;
* cd ~ — перейди в домашнюю директорию (/Users/Username);
* cd / — перейди в корневую директорию.


## Работа с файлами и папками
### Создание
* touch index.html (англ. touch, «коснуться») — создай файл index.html в текущей папке;
* touch index.html style.css script.js — если нужно создать сразу несколько файлов, можно напечатать их имена в одну строку через пробел;
* mkdir second-project (от англ. make directory, «создать директорию») — создай папку с именем second-project в текущей папке.


### Копирование и перемещение
* cp file.txt ~/my-dir (от англ. copy, «копировать») — скопируй файл в другое место;
* mv file.txt ~/my-dir (от англ. move, «переместить») — перемести файл или папку в другое место.


### Чтение
* cat file.txt (от англ. concatenate and print, «объединить и распечатать») — распечатай содержимое текстового файла file.txt.


### Удаление
* rm about.html (от англ. remove, «удалить») — удали файл about.html;
* rmdir images (от англ. remove directory, «удалить директорию») — удали папку images;
* rm -r second-project (от англ. remove, «удалить» + recursive, «рекурсивный») — удали папку second-project и всё, что она содержит.


## Полезные возможности
* Команды необязательно печатать и выполнять по очереди. Можно указать их списком — разделить двумя амперсандами (&&).
* У консоли есть собственная память — буфер с несколькими последними командами. По ним можно перемещаться с помощью клавиш со стрелками вверх (↑) и вниз (↓).
* Чтобы не вводить название файла или папки полностью, можно набрать первые символы имени и дважды нажать Tab. Если файл или папка есть в текущей директории, командная строка допишет путь сама.
Например, вы находитесь в папке dev. Начните вводить cd first и дважды нажмите Tab. Если папка first-project есть внутри dev, командная строка автоматически подставит её имя. Останется только нажать Enter.


[Шпаргалка Git](https://practicum.yandex.ru/profile/git-basics/ "Переход к уроку со шпаргалкой")
---

## Хеш — идентификатор коммита

Git преобразует информацию о коммитах с помощью алгоритма SHA-1 и для каждого из них рассчитывает уникальный идентификатор — хеш.
Хеш — основной идентификатор коммита и позволяет узнать его автора, дату и содержимое закоммиченных файлов.
Все хеши, а также таблицу соответствий хеш → информация о коммите Git хранит в папке .git.

## Лог

* git log - появляется список коммитов.
* git log --oneline - получить сокращенный лог.В сокращённом логе выводятся сокращённые хеши — их можно использовать точно так же, как и полные.

## HEAD

Файл HEAD (англ. «голова», «головной») — один из служебных файлов папки .git. Он указывает на коммит, который сделан последним (то есть на самый новый). 
Вместо хеша последнего коммита можно написать слово HEAD — Git вас поймёт.

## Статусы файлов

* Статусом _untracked_ помечается файл, о существовании которого Git знает, но не следит за изменениями в нём. Этот статус — противоположность tracked, в который попадают все файлы, отслеживаемые Git.
* Файл переходит в статус _staged_ после выполнения git add.
* Статус _modified_ означает, что файл был изменён.
* Большинство файлов в проектах «шагает» по следующему циклу: «изменён» → «добавлен в список на коммит» → «закоммичен» → «изменён» → и так далее.

## Как читать git status

* Команда git status всегда подскажет, что происходит с файлом: например, он добавлен в список «на коммит» или ещё вообще не отслеживается, или изменён.
* git status показывает явно следующие состояния файлов: _untracked, staged и modified._
* git status подсказывает, какие команды можно выполнить, чтобы поменять состояние файла.

## Оформление сообщений к коммитам 

* Для сообщений на *русском* языке часто рекомендуют использовать инфинитивы. Например: _Добавить тесты для PipkaService_, _Исправить ошибку #123_ и так далее.
* Для сообщений на *английском* рекомендуется использовать повелительное наклонение (англ. imperative). Например: _Use library mega_lib_300_, _Fix exit button_ и так далее.

Важно следовать следующим правилам: 
- сообщение коммита легко читается;
- оно информативное;
- все сообщения оформлены в одном стиле.

## Работа с ветками.

## Клонирование чужого репозитория
* git clone git@github.com:YandexPraktikum/first-project.git (от англ. clone, «клон», «копия») — склонируй репозиторий с URL first-project.git из аккаунта YandexPraktikum на мой локальный компьютер.

## Создание веток
* git branch feature/the-finest-branch (от англ. branch, «ветка») — создай ветку от текущей с названием feature/the-finest-branch;
* git checkout -b feature/the-finest-branch — создай ветку feature/the-finest-branch и сразу переключись на неё.

## Навигация по веткам
* git branch (от англ. branch, «ветка») — покажи, какие есть ветки в репозитории и в какой из них я нахожусь (текущая ветка будет отмечена символом *);
* git branch -a — покажи все известные ветки, как локальные (в локальном репозитории), так и удалённые (в origin, или на GitHub).
* git checkout feature/br — переключись на ветку feature/br.

## Сравнение веток
* git diff main HEAD (от англ. difference, «отличие», «разница») — покажи разницу между веткой main и указателем на HEAD;
* git diff HEAD~2 HEAD — покажи разницу между тем коммитом, который был два коммита назад, и текущим.

## Удаление веток
* git branch -d br-name — удали ветку br-name, но только если она является частью main;
* git branch -D br-name — удали ветку br-name, даже если она не объединена с main.

## Слияние веток
* git merge main (от англ. merge, «сливать», «поглощать») — объедини ветку main с текущей активной веткой. 

## Работа с удалённым репозиторием
* git push -u origin my-branch (от англ. push, «толкнуть», «протолкнуть») — отправь новую ветку my-branch в удалённый репозиторий и свяжи локальную ветку с удалённой, чтобы при дополнительных коммитах можно было писать просто git push без -u;
* git push my-branch — отправь дополнительные изменения в ветку my-branch, которая уже существует в удалённом репозитории;
* git pull (от англ. pull, «вытянуть») — подтяни изменения текущей ветки из удалённого репозитория.