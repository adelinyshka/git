**Клонировать репозиторий со всеми ветками**

1. First, clone a remote Git repository and cd into it:

$ git clone git://example.com/myproject
$ cd myproject

2. Next, look at the local branches in your repository

$ git branch
* master

3. But there are other branches hiding in your repository! You can see these using the -a flag:

$ git branch -a

* master
  remotes/origin/HEAD
  remotes/origin/master
  remotes/origin/v1.0-stable
  remotes/origin/experimental

4. If you just want to take a quick peek at an upstream branch, you can check it out directly:

$ git checkout origin/experimental

5. But if you want to work on that branch, you'll need to create a local tracking branch which is done automatically by:

$ git checkout experimental

6. and you will see
$ Branch experimental set up to track remote branch experimental from origin.
Switched to a new branch 'experimental'


Изменить origin адрес репозитория 
- git remote set-url origin <ссылка на репо>

Открыть историю всех коммитов для изменения коммитов 
- git rebase -i --root

**Переместить файлы из одного репозитория в другой с историей коммитов**:
находясь в основном репо
git remote add <имя><путь присоединяемого репо>
git fetch <имя>
git merge <имя>/master --no-commit
(если не мерджит, добваьте в конце --allow-unrelated-histories )

(сливаемый репо в папке, делаем перемещения файлов по папкам если нужно)
git mv <что откуда><куда>

git commit
git push

Индексация изменений - git status

История - git log

История подробно - git log --all --graph --decorate

Получение старых версий - git hist 
предварительно настроив -> git config --global alias.hist "log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short"

Создание тегов версий - git tag <имя_тега>

Теги - git tag

Просмотр Тегов в логах - git hist master --all / git hist

**Отмена локальных изменений** (до индексации) - git checkout <имя_файла_с_изменениями>

**Отмена проиндексированных изменений** (перед коммитом):
  - git reset HEAD <имя_файла_с_изменениями>
  - git checkout <имя_файла_с_изменениями>

**Отмена последнего коммита** - git revert HEAD

Удаление коммитов из ветки:
  - отметить ненужный коммит тегом = git tag <имя_тега>
  - git reset --hard <хэш_нужного_коммита>
  - git tag -d <тег_из_первого_пункта>

Внесение изменений в коммиты - git commit --amend -m "новый коммент"

Перемещение файлов - git mv <имя_файла> <куда_перенести>

Вывод хэша последнего коммита - git hist --max-count=1

Вывод изменений последнего коммита:
  - git cat-file -t <hash> / алиас = git type 
  - git cat-file -p <hash> / алиас = git dump
  
Вывод дерева каталогов/каталога/файлов, ссылка на который идет в коммите - git cat-file -p <хэш_дерева_каталога/каталога/файла>
 
Создание ветки - git checkout -b <имя_ветки>
 
Переключение между ветками - git checkout <имя_ветки>

Вывод веток - git branch

Вывод веток подробно - git hist --all

Слияние веток:
  - переключиться на <сливаемую_ветку>
  - git merge master
  
Разрешение конфликтов:
 - открыть файлы, указанные git и вручную исправить изменения
 - сделать коммит с новыми изменениями
 
Перебазирование - git rebase master 
Не используйте перебазирование:
 - Если ветка является публичной и расшаренной. Переписывание общих веток будет мешать работе других членов команды.
 - Когда важна точная история коммитов ветки (так как команда rebase переписывает историю коммитов).
 
Клонирование репо - git clone <адрес репо> <имя_папки_для_репо>

Список удаленных веток - git branch -a

Слияние изменений с удаленного репо - git pull 
или
 - git fetch
 - git merge origin/master
 
Добавление ветки наблюдения - git branch --track <имя_ветки> origin/<имя_ветки>

Создать чистый репо - git clone --bare <имя_существующего_репо> <имя_чистого_репо>

Расшарить репо в чистый репо - git remote add shared <пусть_ к_удаленному_репо> (находясь в репо)
 
Настроить отслеживание в чистый репо - git branch --track shared master

Извлечь изменения из чистого репо - git pull shared master

Расшарить локально:
 - git daemon --verbose --export-all --base-path=.
 - git clone git://localhost/<имя_репо> <название_новой_папки>
 
 Для Mac os.
На основе https://githowto.com/ru/ и других источников
