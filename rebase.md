# git rebase — построение ровной линии коммитов

Предположим, разработчик завел дополнительную ветку для разработки отдельной возможности и совершил в ней несколько коммитов. Одновременно по какой-либо причине в основной ветке также были совершены коммиты: например, в нее были залиты изменения с удаленного сервера, либо сам разработчик совершал в ней коммиты.

В принципе, можно обойтись обычным `git merge`. Но тогда усложняется сама линия разработки, что бывает нежелательно в слишком больших проектах, где участвует множество разработчиков.

Предположим, имеется две ветки, master и топик, в каждой из которых было совершенно несколько коммитов начиная с момента ветвления. Команда git rebase берет коммиты из ветки topic и накладывает их на последний коммит ветки master.

Вариант, в котором явно указывается, что и куда накладывается:
```
git-rebase master topic
```
на master накладывается активная в настоящий момент ветка:
```
git-rebase master
```
После использования команды история становится линейной. При возникновении конфликтов при поочередном накладывании коммитов работа команды будет останавливаться, а в проблемные местах файлов появятся соответствующие метки. После редактирования, разрешения конфликтов, файлы следует внести в индекс командой:
```
git add
```
и продолжить наложение следующих коммитов командой:
```
git rebase --continue
```
Альтернативными выходами будут команды пропустить наложение коммита и перейти к следующему:
```
git rebase --skip 
```
и отмена работы команды и всех внесенных изменений:
```
git rebase --abort 
```
С ключом -i (--interactive) команда будет работать в интерактивном режиме. Пользователю будет предоставлена возможность определить порядок внесения изменений, автоматически будет вызывать редактор для разрешения конфликтов и так далее.