---
title: Amending the Most Recent Commit Message
localeTitle: Внесение изменений в последнее сообщение об итогах
---
Часто возникает случай, когда последний коммит был представлен досрочно (отсутствует файл, отсутствует изменение в файле и т. Д.), Или сообщение фиксации может быть ошибочным или неполным. Для такого случая Git предлагает флаг `--amend` commit. Чтобы изменить фиксацию, начните с ввода:
```
git commit --amend 
```

Вышеупомянутые действия будут фиксировать любые дополнительные изменения и открывать ваш редактор, позволяя вам изменить сообщение фиксации последнего фиксации. Кроме того, вы можете установить сообщение commit непосредственно в командной строке:
```
git commit --amend -m "New commit message" 
```

Если вы хотите добавить файлы или изменения в commit, вам просто нужно убедиться, что изменения добавлены в этап с `git add` перед запуском команды. Кроме того, если вы хотите добавить все просмотренные, измененные файлы (в постановке или иным образом) и изменить фиксацию, вы можете использовать:
```
git commit --amend -am "New commit message" 
```

Флаг `-a` говорит, чтобы добавить все файлы, которые Git сказал для отслеживания.

## Изменение фиксации после нажатия на удаленный

При использовании флага `--amend` Git заменит последнее коммит новым `--amend` с новым хешем. Это означает, что если вы уже нажали на удаленный компьютер перед внесением поправок, то старый коммит будет отсутствовать в последующих последующих нажатиях, и любое новое нажатие будет отклонено. Способ обойти это `--force` толчок. _ПРИМЕЧАНИЕ: `--force` не следует делать легкомысленно._ Для этого введите:
```
git push <remote> <branch> --force 
```

**Или же**
```
git push <remote> <branch> -f 
```

Принудительное перенаправление перезаписывает удаленную ветвь с состоянием вашего локального. Если на удаленной ветке есть коммиты, которых у вас нет в локальной ветке, вы потеряете их. Это может вызвать проблемы, если другие уже вытащили или клонировали из вашего репо. Если вы считаете, что другие, _возможно_ , уже загрузили исправленный коммит, пожалуйста, координируйте их.

## Смотрите также

*   [git-commit (1) Ручная страница](https://www.kernel.org/pub/software/scm/git/docs/git-commit.html)
*   [Pro Git](https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History)
*   [Переполнение стека](http://stackoverflow.com/questions/179123/edit-an-incorrect-commit-message-in-git/179147#179147)