Git популярная система контроля версий, основной интерфейс консольный
 
 После установки Git
*в командной строке от имени администратора*
git config -- global user.name <*Имя_пользователя*>
git config -- global user.email <*Эл.почта_пользователя*>

### Создание локального репозитория 
*в командной строке от имени администратора*
B: {открытие диска в cmd}
cd <*путь_к_папке*>
git init {теперь папка под контролем Git}

GitHub позволяет загрузить все локальные изменения файлов на компьютере в облако и хранить их там, чтобы другие люди могли получить к ним доступ

  *После установки GitHub*
  
### Создание удаленного репозитория
*в профиле GitHub*
Создать новый репозиторий, настроить приватность, скопировать ссылку на созданный репозиторий 
*в cmd, открыв локальный репозиторий*
git remote add origin <*ссылка_на_удаленный_репозиторий(скопированная)*> {связь между локальным и репозиторием установлена, на локальный добавляется удаленный репозиторий по указанной ссылке}

 Создание локального репозитория, полностью копирующий удаленный(например, написанный другим пользователем)
*в cmd, в папке, в которую необходимо загрузить удаленный репозиторий*
git clone <*ссылка_на удаленный_репозиторий*> {создана локальная копия удаленного репозитория, скачиваются все файлы из удаленного репозитория}

### Основные команды
git status {показывает текущий статус всех несохраненных изменений файлов в репозитории}
git add <*имена_файлов_или_папок к сохранению*> {подготавливает данные файлы к следующему коммиту, добавляя их в "индекс" гита. "Индекс" гита - хранилище файлов, готовых к коммиту}
git status {для отображения файлов, готовых к сохранению(например, для проверки на корректность указанных файлов командой ранее)}
git commit -m <*комментарий*> {запоминает версию(коммит) всех файлов в репозитории из индекса и присваивает ей уникальный код(хэш), по которому затем к это версии можно вернуться}
git log {показывает историю всех коммитов в данной ветке с их хэшами и сообщениями}
git checkout <*хэш коммита*> {возврат к любому коммиту}
git push origin(/<*имя удаленного репозитория*>) master(/<*название ветки*>) {публикует коммиты из локального репозитория в удаленный с данным именем в данной ветке}
git pull origin(/<*имя удаленного репозитория*>) master(/<*название ветки*>) {скачивает из данного удаленного репозитория все коммиты в данной ветке, которых еще нет в локальном репозитории}
git branch {выводит список локальных веток, доступных прямо сейчас в данном локальном репозитории}
git brunch <*имя ветки*> {создает новую локальную ветку из той, на которой находишься; по умолчанию создается на основе последнего коммита, на которой находились изначально}
git checkout *имя ветки* {переход на другую ветку}

### Слияние веток
*есть основная ветка master и ветка с изменениями feature*
1 способ(слияние в один коммит):
1. git checkout master {переход в ветку, в которую нежно добавить изменения с ветки feature}
2. git merge {производит слияние данной ветки, на которой прямо сейчас находимся в виде одного нового коммита в текущею версию}
 2 способ(если важна история коммитов): 
  1. git checkout master {переход в ветку, в которую нежно добавить изменения с ветки feature}
  2. git rebase feature {перемещает коммиты из данной ветки в ту, на которой сейчас находимся}

### Основные термины
 Cmd - командная строка, всегда открывается от имени администратора
 Репозиторий - папка с файлами, за которыми следит GIt. Может быть локальным и удаленным(связь между ними обеспечивает Git)
 Ветка - последовательность коммитов, имеющая название. Самая главная master или main



