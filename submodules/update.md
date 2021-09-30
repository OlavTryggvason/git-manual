# Обновление подмодулей

Подмодуль ссылается на конкретную коммит в другом репозитории. Чтобы получить точное состояние всех подмодулей необходимо запустить:
```
git submodule update --recursive
```
Для получения состояния последнего коммита всех подмодулей необходимо выполнить следующую команду:
```
git submodule foreach git pull origin master
```
или использовать аргументы по умолчанию команды git pull:
```
git submodule foreach git pull
```
Эта команда просто обновляет локальную рабочую копию. При запуске команды git status каталоги подмодулей будут показаны изменёнными. Чтобы обновить репозиторий необходимо зафиксировать изменения:
```
git add submodule_directory
git commit
```
Для получения состояние последнего коммита конкретного подмодуля необходимо использовать команду:
```
git submodule update --remote submodule_directory
```