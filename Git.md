# Git

[Сайт](https://git-scm.com/), [Учебник](https://git-scm.com/book/ru/v2)



`git init` - создает в текущем каталоге новый подкаталог с именем .git, создает git - репозиторий.
`git status` - состояние проекта, измененные и не добавленные файлы, индексированные файлы.
`git add имя_файла` - индексация изменений, начинает отслеживать введенный файл.
`git add .` - вносит в индекс все изменения, включая новые файлы.
`git commit -m 'описание изменений'` - создание коммита.
`git fetch`
`git checkout master` - переключение на ветку
`git pull`
`git branch` - все ветки локального репозитория
`git checkout bugfix/00-00271678` - переключение на ветку
`git merge master`- мержует



https://javarush.ru/groups/posts/2683-nachalo-rabotih-s-git-podrobnihy-gayd-dlja-novichkov

https://gist.github.com/rdnvndr/cb21a06c5a71fd71213aed1619380b8e

https://tproger.ru/translations/git-quick-start/

https://habr.com/ru/company/skillbox/blog/442260/

https://habr.com/ru/post/273897/





В чем отличие между `git push -u origin master` и `git push origin master`? Зачем ключ `-u` для команды `git push`?

В том случае, если ветка master (или branch_name) не является отслеживаемой веткой origin/master (или origin/branch_name), а вы хотите сделать её таковой.

Выполнив команду `git push -u origin master` вы устанавливаете связь между той веткой, в которой вы находитесь и веткой *master* на удалённом сервере. Команду требуется выполнить единожды, чтобы потом можно было отправлять/принимать изменения лишь выполняя `git push` из ветки без указания всяких алиасов для сервера и удалённых веток. Это сделано для удобства.
