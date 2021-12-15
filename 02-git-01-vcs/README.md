
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

Добавление .gitignore (само содержиое можно посмотреть в репозитории, добавлены terraform, vscode, python, idea)

```bash
04:52:21 awex@beelink DVPSPDC-3 ±|main|→ git status
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore

nothing added to commit but untracked files present (use "git add" to track)
05:00:40 awex@beelink DVPSPDC-3 ±|main ✗|→ git add .gitignore
05:03:25 awex@beelink DVPSPDC-3 ±|main ✗|→ git commit -m "Added .gitignore"
[main 2f63be0] Added .gitignore
 1 file changed, 279 insertions(+)
 create mode 100644 .gitignore
05:04:09 awex@beelink DVPSPDC-3 ±|main|→
```

Эксперементируем с `git mv` и 'git rm'

```bash
05:10:11 awex@beelink 02-git-01-vcs ±|main ✗|→ echo "will_be_deleted" >> will_be_deleted
05:10:49 awex@beelink 02-git-01-vcs ±|main ✗|→ echo "will_be_moved" >> will_be_moved.txt
05:12:08 awex@beelink 02-git-01-vcs ±|main ✗|→ echo "will_be_deleted" >> will_be_deleted.txt
05:12:14 awex@beelink 02-git-01-vcs ±|main ✗|→ git add *
05:13:41 awex@beelink 02-git-01-vcs ±|main ✗|→ git status
On branch main
Your branch is ahead of 'origin/main' by 4 commits.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md
        new file:   will_be_deleted.txt
        new file:   will_be_moved.txt

05:14:02 awex@beelink 02-git-01-vcs ±|main ✗|→ git commit -m "Prepare to delete and move"
[main 7735131] Prepare to delete and move
 3 files changed, 23 insertions(+)
 create mode 100644 02-git-01-vcs/will_be_deleted.txt
 create mode 100644 02-git-01-vcs/will_be_moved.txt
05:14:12 awex@beelink 02-git-01-vcs ±|main|→ git rm will_be_deleted.txt
rm '02-git-01-vcs/will_be_deleted.txt'
05:18:51 awex@beelink 02-git-01-vcs ±|main ✗|→ git mv will_be_moved.txt has_been_moved.txt
05:20:04 awex@beelink 02-git-01-vcs ±|main ✗|→ git status
On branch main
Your branch is ahead of 'origin/main' by 5 commits.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        renamed:    will_be_moved.txt -> has_been_moved.txt
        deleted:    will_be_deleted.txt

05:20:09 awex@beelink 02-git-01-vcs ±|main ✗|→ git commit -m "Moved and deleted"
[main 6c64e1b] Moved and deleted
 2 files changed, 1 deletion(-)
 rename 02-git-01-vcs/{will_be_moved.txt => has_been_moved.txt} (100%)
 delete mode 100644 02-git-01-vcs/will_be_deleted.txt
 ```

Проверка изменений.

```bash
05:20:58 awex@beelink 02-git-01-vcs ±|main|→ git log
commit 6c64e1b9e123132bc3a4dd55addb02e148a32d88 (HEAD -> main)
Author: AweX <a.v.knyazev@gmail.com>
Date:   Wed Dec 15 17:20:58 2021 +0300

    Moved and deleted

commit 77351315c7de8bce5ef9632e5f891d982725dcfc
Author: AweX <a.v.knyazev@gmail.com>
Date:   Wed Dec 15 17:14:12 2021 +0300

    Prepare to delete and move

commit 2f63be06fbc2df11a552ac86325d0624875c9f78
Author: AweX <a.v.knyazev@gmail.com>
Date:   Wed Dec 15 17:04:09 2021 +0300

    Added .gitignore

commit 365b2e2aa81994b2ad3c46f49ae7948d833e76fb
Author: AweX <a.v.knyazev@gmail.com>
Date:   Wed Dec 15 16:52:21 2021 +0300

    02-git-01-vcs

commit 6d098dccb3ca9692fb976e22fe9e67fcaf102a15
Author: AweX <a.v.knyazev@gmail.com>
Date:   Wed Dec 15 16:36:17 2021 +0300

    fix errors in /README.md

commit eb2f75493361f611aefabfb67b527179c378ea32
Author: AweX <a.v.knyazev@gmail.com>
Date:   Wed Dec 15 16:34:25 2021 +0300

    02-git-01-vcs

commit 5f23cb7a3f71e21a956f1f1ce0004aaa761585a4 (origin/main, origin/HEAD)
Author: AweX <a.v.knyazev@gmail.com>
Date:   Tue Dec 7 22:11:47 2021 +0300

    01-intro-01

commit bb807b60b273bc0b5eb017d7558bd04c41fe3556
Author: iAweX <50710418+iAweX@users.noreply.github.com>
Date:   Tue Dec 7 20:06:21 2021 +0300

    Initial commit
```

### Задание №2 – Знакомство с документаций

Вывод комманд `help`. Как вариант я использую несколько другой синтаксис: `git help gitignore`
