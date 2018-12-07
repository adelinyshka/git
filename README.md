# git команды

`add` — добавить файл или папку в репозиторий git;

`am`
    — применить все патчи из email;

`archive` 
    — создать архив файлов;

`bisect` 
    — использовать бинарный поиск для поиска нужного коммита;

`branch` 
    — управление ветками проекта;

`bundle` — перемещение объектов и ссылок в архиве;

`checkout` — переключение между ветками;

`cherry-pick` — внести изменения в уже существующие коммиты;

`clean` — удалить все неотслеживаемые файлы и папки проекта;

`clone` — создать копию удаленного репозитория в папку;

`commit` — сохранить изменения в репозиторий;

`diff` — посмотреть изменения между коммитами;

`fetch` — скачать удаленный репозиторий;

`init` — создать репозиторий;

`merge` — объединить две ветви;

`pull` — интегрировать удаленный репозиторий с локальным;

`push` — отправить изменения в удаленный репозиторий;

`tag` — управление тегами;

`worktree` — управление деревнями разработки.

`git add -A `
добавить все, что находится в директории

`git commit -m "описание того, что мы поменяли"`
коммит построчно

`git remote add origin`
подключение к удаленному репозиторию

`git push origin master`
отправка изменений на сервер

`git clone`
клонирование репозитория

`git pull origin master`
скачать измененный репозиторий

`git branch имя_новой_ветки`
создать новую ветку в репозитории

`git branch`
какие ветки есть

`git checkout имя_ветки`
переключение между ветками

`git checkout master`
    git merge имя_измененной_ветки
    объединение веток и применение изменений к основной ветке

`git branch -d имя_ветки`
удаление ненужной ветки

`git log`
вывод логов с коммитами

`git show первые_символы_лога`
вывод измнений в логе

`git diff символы_лога..символы_другого_лога`
чтобы увидеть разницу между двумя коммитами

`git checkout символы_лога путь_к_файлу`
возвращение файла к предыдущему состоянию

`git revert HEAD`
Эта команда создаст коммит, отменяющий изменения

`git revert символы_лога`
Эта команда создаст коммит, отменяющий изменения, совершенные в коммите с заданным идентификатором

`git log ‐‐no-merges`
Эта команда показывает всю историю коммитов, но пропускает те, в которых произошли слияния двух веток, 
или где был решен конфликт фиксации. 

`git diff -w`
часто происходят изменения из-за tab текстового редактора. Чтобы игнорировать различия, вызванные 
пробелами при сравнении строк, можно использовать команду с -w.

`git revert ‐‐no-commit [commit]`
Git revert создает новый коммит с содержимым, полученным из всех существующих коммитов, которые были
им отменены. Если вы хотите обратить названный комит и избежать автоматических, можете использовать 
‐‐no-commit или сокращение -n.

`git diff ‐‐stat`
Показывает, как каждый файл был изменен за определенное время. Вы можете добавить 3 параметра: width
для определения ширины вывода по умолчанию, name-width для установки ширины имени файла и count для 
ограничения вывода на первое число строк.

`git reset ‐‐soft HEAD^`

Сбросьте head до определенного коммита, не касаясь индексного файла и рабочего дерева. Все изменения, 
сделанные после этой фиксации, переносятся на этап “поставлены для коммита”. Далее вам просто нужно 
запустить git commit, чтобы добавить их обратно.

`git stash branch [branch-name] [stash]`
Эта команда создает новую ветку с именем branch-name и проверяет ее, а затем применяет к ней изменения 
от заданного stash и сбрасывает его. Если ни один stash не указан, используется последний. Это позволяет 
применять любые спрятанные изменения в более безопасной среде, которая впоследствии может быть объединена 
с мастером.

`git branch -a`
Команда показывает список всех удаленных и локальных ветвей. Вы можете использовать флаг ‐‐merged, чтобы 
видеть только те ветки, которые полностью объединены с главной. Таким образом, вы можете отслеживать свои
ветки и узнавать, какие из них больше не используются, и могут быть удалены.

`git commit ‐‐amend`
С помощью git commit ‐‐amend вы можете изменить свой предыдущий коммит, вместо того чтобы создавать новый. 
Если вы не внесли свои изменения в удаленную ветку, можете использовать эту команду для внесения изменений 
в последний коммит, добавления последних изменений и даже изменения сообщения о коммите.

`git pull ‐‐rebase`
Git pull ‐‐rebase заставляет git сначала вытащить изменения, а затем переустановить разблокированные коммиты
поверх последней версии удаленной ветки. Параметр ‐‐rebase может использоваться для создания линейной истории,
избегая ненужных фиксаций.

`git add -p`
Когда вы используете эту команду вместо немедленного добавления всех совершенных изменений, система спрашивает,
что сделать с каждым из них. Таким образом, вы сможете сами выбрать, что именно хотите закоммитить.

`git log` +
`-p`Выводит патч (заплатку/diff) внесенный каждым коммитом.

`--stat`Выводит статистику по файлам измененным в каждом коммите.

`--shortstat`Отображает только строку с changed/insertions/
deletions от вывода команды `--stat`.

`--name-only`Выводит список измененных файлов после каждого коммита.

`--name-status`Выводит список файлов вместе с информацией о добавлении/изменении/
удалении.

`--abbrev-commit`Выводит только первые несколько символов контрольной суммы SHA-1 вместо всех 40.

`--relative-date`Выводит дату в относительном формате (например, “2 недели назад”) вместо использования полного формата даты.

`--graph`Выводит ASCII граф истории ветвлений и слияний рядом с выводом лога.

`--pretty`Выводит коммиты в альтернативном формате. Параметры включают oneline, short, full, fuller, и format (где вы можете указать свой собственный формат).

`git log --pretty=format`

Параметр / Описание выводимых данных

`%H`Хеш коммита

`%h`Сокращенный хеш коммита

`%T`Хеш дерева

`%t`Сокращенный хеш дерева

`%P`Хеши родительских коммитов

`%p`Сокращенные хеши родительских коммитов

`%an`Имя автора

`%ae`Электронная почта автора

`%ad`Дата автора (формат соответствует параметру --date= )

`%ar`Дата автора, относительная (пр. "2 мес. назад")

`%cn`Имя коммитера

`%ce`Электронная почта коммитера

`%cd`Дата коммитера

`%cr`Дата коммитера, относительная

`%s`Комментарий

+

`grep` позволяет искать по ключевым словам в сообщении

`--since`, `--after`Ограничить коммиты теми, которые сделаны после указанной даты.

`--until`, `--before`Ограничить коммиты теми, которые сделаны до указанной даты.

`--author`Показать только те коммиты, автор которых соответствует указанной строке.

`--committer`Показать только те коммиты, коммитер которых соответствует указанной строке.

by Scott Chacon Pro Git
