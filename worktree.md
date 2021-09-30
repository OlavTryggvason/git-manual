# git worktree - одновременная работа с несколькими ветками

Git позволяет работать одновременно с несколькими ветками одного репозитория. Для добавления ветки в отдельную директорию необходимо выполнить команду:
```
git worktree add path/ remote/master
```
Для просмотра всех директориев с ветками можно воспользоваться командой:
```
git worktree list
```
Директорию с веткой можно перести в другое место с помощью команды:
```
git worktree move old-path/ new-path/
```
После окончания работы с веткой в директории, её можно удалить командой:
```
git worktree remove path/
```