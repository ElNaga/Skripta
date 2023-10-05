# Научете Git чекори


1. Поставување на Repo:
Иницијализира нов Git репозиториум и се извршува првиот commit на датотеката.
Чекори:
1. Креирајте нов директориум за проектот.

```
mkdir MyBookProject
cd MyBookProject
```

Ова креира директориум за нашите датотеки на проектот.

2. Иницијализирајте Git репозиториум.

```
git init
```

Оваа команда иницијализира нов Git репозиториум во тековниот директориум.

3. Креирајте го првото поглавје од книгата.

```
echo "This is intro." > chapter1.txt
```

Командата `echo` ја печати дадената текст, и `>` го пренасочува овој текст кон датотека наречена `chapter1.txt`.

4. Следете и commit-ирајте ја новата датотека.

```
git add chapter1.txt
git commit -m "Add chapter 1: Introduction"
```

`git add` го поставува фајлот за commit, и `git commit` креира нов commit со поставените промени.

2. Вовед во Git гранки:
Го воведува поимот на гранкањето со креирање на нова гранка.
Чекори:
1. Креирајте и префрлете се на нова гранка наречена `chapter2`.

```
git checkout -b chapter2
```

Командата `checkout -b` креира нова гранка и веднаш се префрла на неа.

3. Гранкање на функционалности:
Го демонстрира концептот на работа на нови функционалности во одделни гранки.
Чекори:
1. Напишете го второто поглавје во гранката `chapter2`.

```
echo "This is the second chapter." > chapter2.txt
```

2. Ставете ги промените и commit-ирајте.

```
git add chapter2.txt
git commit -m "Add chapter 2"
```

4. Спојување на гранки:
Ги спојува промените од гранката за функционалности во главната гранка.
Чекори:
1. Префрлете се назад на главната гранка `main`.

```
git checkout main
```

2. Спојте ја гранката `chapter2` во главната гранка `main`.

```
git merge chapter2
```

Оваа команда интегрира промени од наведената гранка (`chapter2`) во тековната гранка (`main`).

5. GitHub PRs:
Го воведува концептот за Pull Requests во GitHub.
Чекори:
1. Испратете гранката `chapter2` на GitHub.

```
git push origin chapter2
```

Ова ја праќа нашата гранка на онлајн репото.

2. На веб-сајтот на GitHub, одете до репозиториумот и демонстрирајте како да отворите pull request од `chapter2` до `main`. Овој чекор вклучува:
Кликнување на "Pull requests".Одбирање "New pull request".Одбирање на гранката `chapter2` и предлагање на pull request.
	- Кликнување на "Pull requests".
	- Одбирање "New pull request".
	- Одбирање на гранката `chapter2` и предлагање на pull request.


6. Тимско работење и разрешување на конфликти во код:
Го демонстрира сценариото каде двајца членови на тимот прават конфликтни промени.
Чекори:
1. Креирајте нова гранка за `chapter3`.

```
git checkout -b chapter3
```

2. Напишете содржина за `chapter3`.

```
echo "This is chapter 3 written by Alice." > chapter3.txt
git add chapter3.txt
git commit -m "Add chapter 3 by Alice"
```

3. Сега, ќе симулираме внес од друг член на тимот. Префрлете се на `main`, и направете конфликтни промени.

```
git checkout main
echo "This is chapter 3 written by Bob." > chapter3.txt
git add chapter3.txt
git commit -m "Add chapter 3 by Bob"
```

Обидете се да го споите `chapter3` гранката во `main`.

```
git merge chapter3
```

Во овој момент, Git ќе информира за конфликт при спојувањето.
Отворете го спротивниот фајл (во овој случај, chapter3.txt) со било кој текст уредник. Ќе видите обележувачи за конфликт (<<<<<<<, =======, >>>>>>>) кои ги обележуваат различните содржини. Модифицирајте го фајлот за да го разрешите конфликтот, зачувајте и потоа продолжете со спојувањето.

Завршете со спојувањето.

```
git add chapter3.txt
git commit
```

Ова ќе отвори уредник со стандардна порака за спојување. Зачувајте и излезете за да го завршите спојувањето.
7. Откривање на виновникот (blame):
Што прави: Открива кој направил која промена.
Чекори:
Користете ја blame командата на `chapter1.txt`.

```
git blame chapter1.txt
```

Ова покажува анотации за секоја линија, која го индицира последниот commit кој ја модифицирал линијата и кој бил авторот.
8. Откривање на разлики (diff):
Што прави: Покажува промени помеѓу commits.
Чекори:
Покажете разлики помеѓу `main` и `chapter3` гранките за `chapter3.txt`.

```
git diff main..chapter3 -- chapter3.txt
```

Ова покажува разлики помеѓу двете гранки за специфицираниот фајл.
9. .gitignore конфигурација:
Што прави: Поставува фајл за да се назначат намерно непратени фајлови кои Git треба да ги игнорира.
Чекори:
Креирајте .gitignore фајл за да ги игнорирате резервните фајлови.

```
echo "*.bak" > .gitignore
git add .gitignore
git commit -m "Add .gitignore to exclude backup files"
```
