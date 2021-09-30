# git checkout — переключение между ветками, извлечение файлов

Команда git checkout позволяет переключаться между последними коммитами (если упрощенно) веток:
```
checkout some-other-branch
```
Создаёт ветку, в которую и произойдет переключение:
```
git checkout -b some-other-new-branch
```
Если в текущей ветке были какие-то изменения по сравнению с последним коммитом в ветке(HEAD), то команда откажется производить переключение, дабы не потерять произведенную работу. Проигнорировать этот факт позволяет ключ -f:
```
git checkout -f some-other-branch
```
В случае, когда изменения надо все же сохранить, следует использовать ключ -m. Тогда команда перед переключением попробует залить изменения в текущую ветку и, после разрешения возможных конфликтов переключиться в новую:
```
git checkout -m some-other-branch
```
Вернуть файл (или просто вытащить из прошлого коммита) позволяет команда вида:
```
git checkout somefile
```
Возвращает somefile к состоянию последнего коммита:
```
git checkout somefile
```
Возвращает somefile к состоянию на два коммита назад по ветке:
```
git checkout HEAD~2 somefile
```