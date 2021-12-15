
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
04:22:48 awex@beelink DVPSPDC-3 ±|main ✗|→ git diff 02-git-01-vcs/README.md
diff --git a/02-git-01-vcs/README.md b/02-git-01-vcs/README.md
index a04b81f..29b9566 100644
--- a/02-git-01-vcs/README.md
+++ b/02-git-01-vcs/README.md
@@ -86,3 +86,6 @@ Changes to be committed:

+
+11. Просто какие-то изменения
```

11. Так как проверять все долго и неинтересно напишу просто, что `git diff` покажет изменеия между текущим и зафиксированным, а `git diff --staged` между зафиксированным и закоммиченным.

12. Доделаем все изменения, проверим и закоммитим

```bash
04:23:33 awex@beelink DVPSPDC-3 ±|main ✗|→ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   02-git-01-vcs/README.md

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

04:33:44 awex@beelink DVPSPDC-3 ±|main ✗|→ git add 02-git-01-vcs/README.md 
04:34:05 awex@beelink DVPSPDC-3 ±|main ✗|→ git commit -m "02-git-01-vcs"
[main eb2f754] 02-git-01-vcs
 1 file changed, 88 insertions(+)
 create mode 100644 02-git-01-vcs/README.md
04:34:25 awex@beelink DVPSPDC-3 ±|main ✗|→ git status 
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
04:35:09 awex@beelink DVPSPDC-3 ±|main ✗|→ git add README.md
04:35:20 awex@beelink DVPSPDC-3 ±|main ✗|→ git commit -m "fix errors in /README.md"
[main 6d098dc] fix errors in /README.md
 1 file changed, 1 insertion(+), 1 deletion(-)
04:36:17 awex@beelink DVPSPDC-3 ±|main|→
```
