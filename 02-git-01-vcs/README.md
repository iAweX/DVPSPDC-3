
# Домашнее задание к занятию «2.1. Системы контроля версий.»

## Задание №1 – Создать и настроить репозиторий для дальнейшей работы на курсе

Создание репозитария и коммиты

1. [Репозитарий](https://github.com/iAweX/DVPSPDC-3) был создан еще на этапе выполнения 01-intro-01

2. Клонирование репозитария 

```bash
01:47:08 awex@beelink netology → git clone https://github.com/iAweX/DVPSPDC-3.git DVPSPDC-3
Cloning into 'DVPSPDC-3'...
remote: Enumerating objects: 15, done.
remote: Total 15 (delta 0), reused 0 (delta 0), pack-reused 15
Receiving objects: 100% (15/15), 1.06 MiB | 633.00 KiB/s, done.
```

3. Переход в каталог репозитария

```bash
03:25:04 awex@beelink netology → cd DVPSPDC-3/
/home/awex/netology/DVPSPDC-3
03:34:19 awex@beelink DVPSPDC-3 ±|main|→ 
```

4. Первоначальная настройка
  
```bash
03:34:19 awex@beelink DVPSPDC-3 ±|main|→ git config --global user.email "a.v.knyazev@gmail.com"
03:36:52 awex@beelink DVPSPDC-3 ±|main|→ git config --global user.name "AweX"
```

5. Просмотр `git status`

```bash
03:37:10 awex@beelink DVPSPDC-3 ±|main|→ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

6. Редактирование README.md

```bash
03:39:17 awex@beelink DVPSPDC-3 ±|main|→ code 02-git-01-vcs/README.md
```

7. Вывод `git status`

```bash
03:42:13 awex@beelink DVPSPDC-3 ±|main|→ git status
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        02-git-01-vcs/

nothing added to commit but untracked files present (use "git add" to track)
04:05:16 awex@beelink DVPSPDC-3 ±|main ✗|→
```

8. Добавляем 02-git-01-vcs/ в отслеживание

```bash
04:05:16 awex@beelink DVPSPDC-3 ±|main ✗|→ git add 02-git-01-vcs/
```

9. Проверяем `git status`

```bash
04:08:06 awex@beelink DVPSPDC-3 ±|main ✗|→ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   02-git-01-vcs/README.md

04:08:56 awex@beelink DVPSPDC-3 ±|main ✗|→
```

10. Добавляем строки в 02-git-01-vcs/README.md и смотрим diff

```diff
