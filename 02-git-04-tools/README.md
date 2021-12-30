# Домашнее задание к занятию «2.4. Инструменты Git»

#### Клонирование репозитария terraform

```bash
12:41:09 AweX@HOST Netology → git clone https://github.com/hashicorp/terraform.git
Cloning into 'terraform'...
remote: Enumerating objects: 254106, done.
remote: Counting objects: 100% (20/20), done.
remote: Compressing objects: 100% (11/11), done.
remote: Total 254106 (delta 15), reused 9 (delta 9), pack-reused 254086
Receiving objects: 100% (254106/254106), 186.54 MiB | 19.49 MiB/s, done.
Resolving deltas: 100% (157678/157678), done.
Updating files: 100% (2971/2971), done.
12:42:10 AweX@HOST Netology →
12:42:10 AweX@HOST Netology → cd terraform/
/c/Users/AweX/Netology/terraform
12:42:33 AweX@HOST terraform ±|main|→
```

#### 1. Поиск полного хеша и описания коммита, хеш которого начинается с `aefea`

- Способ 1. Подставить начало хеша в `git show`

```bash
12:53:24 AweX@HOST terraform ±|main|→ git show aefea
commit aefead2207ef7e2aa5dc81a34aedf0cad4c32545
Author: Alisdair McDiarmid <alisdair@users.noreply.github.com>
Date:   Thu Jun 18 10:29:58 2020 -0400

    Update CHANGELOG.md

diff --git a/CHANGELOG.md b/CHANGELOG.md
index 86d70e3e0..588d807b1 100644
--- a/CHANGELOG.md
+++ b/CHANGELOG.md
@@ -27,6 +27,7 @@ BUG FIXES:
 * backend/s3: Prefer AWS shared configuration over EC2 metadata credentials by default ([#25134](https://github.com/hashicorp/terraform/issues/25134))
 * backend/s3: Prefer ECS credentials over EC2 metadata credentials by default ([#25134](https://github.com/hashicorp/terraform/issues/25134))
 * backend/s3: Remove hardcoded AWS Provider messaging ([#25134](https://github.com/hashicorp/terraform/issues/25134))
+* command: Fix bug with global `-v`/`-version`/`--version` flags introduced in 0.13.0beta2 [GH-25277]
 * command/0.13upgrade: Fix `0.13upgrade` usage help text to include options ([#25127](https://github.com/hashicorp/terraform/issues/25127))
 * command/0.13upgrade: Do not add source for builtin provider ([#25215](https://github.com/hashicorp/terraform/issues/25215))
 * command/apply: Fix bug which caused Terraform to silently exit on Windows when using absolute plan path ([#25233](https://github.com/hashicorp/terraform/issues/25233))
12:53:33 AweX@HOST terraform ±|main|→
```

- Способ 2. Вывести `git log` и перенаправить в grep

```bash
01:06:21 AweX@HOST terraform ±|main|→ git log --pretty=format:"%H %s" | grep '\<aefea'
aefead2207ef7e2aa5dc81a34aedf0cad4c32545 Update CHANGELOG.md
01:08:36 AweX@HOST terraform ±|main|→
```

#### 2. Поиск соответствия коммита тегу `85024d3`

- Способ 1. Используем `git describe`

```bash
01:43:32 AweX@HOST terraform ±|main|→ git describe --exact-match 85024d3
v0.12.23
```

- Способ 2. Используем `git show`

```bash
02:03:46 AweX@HOST terraform ±|main|→ git show 85024d3
commit 85024d3100126de36331c6982bfaac02cdab9e76 (tag: v0.12.23)
Author: tf-release-bot <terraform@hashicorp.com>
Date:   Thu Mar 5 20:56:10 2020 +0000

    v0.12.23

diff --git a/CHANGELOG.md b/CHANGELOG.md
index 1a9dcd0f9..faedc8bf4 100644
--- a/CHANGELOG.md
+++ b/CHANGELOG.md
@@ -1,4 +1,4 @@
-## 0.12.23 (Unreleased)
+## 0.12.23 (March 05, 2020)
 ## 0.12.22 (March 05, 2020)

 ENHANCEMENTS:
diff --git a/version/version.go b/version/version.go
index 33ac86f5d..bcb6394d2 100644
--- a/version/version.go
+++ b/version/version.go
@@ -16,7 +16,7 @@ var Version = "0.12.23"
 // A pre-release marker for the version. If this is "" (empty string)
 // then it means that it is a final release. Otherwise, this is a pre-release
 // such as "dev" (in development), "beta", "rc1", etc.
-var Prerelease = "dev"
+var Prerelease = ""

 // SemVer is an instance of version.Version. This has the secondary
 // benefit of verifying during tests and init time that our version is a
02:03:59 AweX@HOST terraform ±|main|→
```

#### 3. Поиск родителей коммита `b8d720`

- Способ 1. Используем `git show`. Ответ в строке `Merge: 56cd7859e 9ea88f22f`

```bash
02:34:10 AweX@HOST terraform ±|main|→ git show b8d720
commit b8d720f8340221f2146e4e4870bf2ee0bc48f2d5
Merge: 56cd7859e 9ea88f22f
Author: Chris Griggs <cgriggs@hashicorp.com>
Date:   Tue Jan 21 17:45:48 2020 -0800

    Merge pull request #23916 from hashicorp/cgriggs01-stable

    [Cherrypick] community links

02:34:17 AweX@HOST terraform ±|main|→
```

- Способ 2. Используем `git log`. 

```bash
02:38:36 AweX@HOST terraform ±|main|→ git log --pretty=format:'%h %P' | grep '^\<b8d720'
b8d720f83 56cd7859e05c36c06b56d013b55a252d0bb7e158 9ea88f22fc6269854151c571162c5bcf958bee2b
02:48:04 AweX@HOST terraform ±|main|→
```

#### 4. Перечислим хеши и комментарии всех коммитов которые были сделаны между тегами v0.12.23 и v0.12.24

```bash
03:11:29 AweX@HOST terraform ±|main|→ git log --oneline v0.12.23..v0.12.24
33ff1c03b (tag: v0.12.24) v0.12.24
b14b74c49 [Website] vmc provider links
3f235065b Update CHANGELOG.md
6ae64e247 registry: Fix panic when server is unreachable
5c619ca1b website: Remove links to the getting started guide's old location
06275647e Update CHANGELOG.md
d5f9411f5 command: Fix bug when using terraform login on Windows
4b6d06cc5 Update CHANGELOG.md
dd01a3507 Update CHANGELOG.md
225466bc3 Cleanup after v0.12.23 release
03:11:40 AweX@HOST terraform ±|main|→
```

#### 5. Ищем коммит в котором была создана функция providerSource

```diff
04:12:16 AweX@HOST terraform ±|main|→ git log --oneline -S 'func providerSource('
8c928e835 main: Consult local directories as potential mirrors of providers
05:09:30 AweX@HOST terraform ±|main|→ git show 8c928e835 | grep 'func providerSource('
+func providerSource(services *disco.Disco) getproviders.Source {
05:10:56 AweX@HOST terraform ±|main|→
```

Ответ: 8c928e835

#### 6. Ищем все коммиты, в которых была изменена функция globalPluginDirs

```bash
04:54:26 AweX@HOST terraform ±|main|→ git grep -p 'func globalPluginDirs('
plugins.go=import (
plugins.go:func globalPluginDirs() []string {
04:59:06 AweX@HOST terraform ±|main|→ git log -s -L :globalPluginDirs:plugins.go --oneline
78b122055 Remove config.go and update things using its aliases
52dbf9483 keep .terraform.d/plugins for discovery
41ab0aef7 Add missing OS_ARCH dir to global plugin paths
66ebff90c move some more plugin search path logic to command
8364383c3 Push plugin discovery down into command package
04:59:12 AweX@HOST terraform ±|main|→
```

#### 7. Ищем автора функции synchronizedWriters

```diff
05:34:49 AweX@HOST terraform ±|main|→ git log --pretty=format:"Commit: %h Message: %s, Author: %an (%ae), %ar" -S 'func synchronizedWriters('
Commit: bdfea50cc Message: remove unused, Author: James Bardin (j.bardin@gmail.com), 1 year, 1 month ago
Commit: 5ac311e2a Message: main: synchronize writes to VT100-faker on Windows, Author: Martin Atkins (mart@degeneration.co.uk), 4 years, 8 months ago
05:35:30 AweX@HOST terraform ±|main|→ git show 5ac311e2a | grep 'func synchronizedWriters('
+func synchronizedWriters(targets ...io.Writer) []io.Writer {
05:36:44 AweX@HOST terraform ±|main|→ git show bdfea50cc | grep 'func synchronizedWriters('
-func synchronizedWriters(targets ...io.Writer) []io.Writer {
05:37:02 AweX@HOST terraform ±|main|→
```

Ответ: Author: Martin Atkins (mart@degeneration.co.uk), 4 years, 8 months ago