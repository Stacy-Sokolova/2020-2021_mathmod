---
lang: ru-RU
sansfont: PT Sans
indent: true
subtitle: Работа с git
romanfontoptions: Ligatures=TeX
lot: true
polyglossia-lang: russian
toc_depth: '2'
header-includes:
  - \linepenalty=10
  - \interlinepenalty=0
  - \hyphenpenalty=50
  - \exhyphenpenalty=50
  - \binoppenalty=700
  - \relpenalty=500
  - \clubpenalty=150
  - \widowpenalty=150
  - \displaywidowpenalty=50
  - \brokenpenalty=100
  - \predisplaypenalty=10000
  - \postdisplaypenalty=0
  - \floatingpenalty = 20000
  - \raggedbottom
  - '\usepackage{float}'
  - '\floatplacement{figure}{H}'
monofont: PT Mono
mainfont: PT Serif
romanfont: PT Serif
sansfontoptions: 'Ligatures=TeX,Scale=MatchLowercase'
toc-title: Содержание
lof: true
polyglossia-otherlangs: english
toc: true
mainfontoptions: Ligatures=TeX
monofontoptions: Scale=MatchLowercase
papersize: a4paper
fontsize: 12pt
documentclass: scrreprt
linestretch: '1.5'
pdf-engine: lualatex
title: Отчёт по лабораторной работе №1
author: Соколова Анастасия Витальевна
---

Цель работы
===========

Цель данной лабораторной работы --- освоение работы с системой контроля версий
git, с помощью которой можно удобно и эффективно отслеживать и фиксировать
изменения в файлах или проектах.

Задание
=======

-   Создание аккаунта на Github.

-   Установка ssh-ключа.

-   Создание репозитория

-   Работа с версиями файлов

Выполнение лабораторной работы
==============================

1.Создан аккаунт на Github и репозиторий для будущих работ (рис. [-@fig:001])

![Аккаунт Github](image/01.jpg)

2.Установлен git, введено имя и почта (рис. [-@fig:002])

![Команды установки имени и почты](image/02.jpg)

3.Установлен ssh-ключ при помощи команд (рис. [-@fig:003]) 1.ssh-keygen -t rsa
-b 4096 -C "stacysv17\@gmail.com" *генерация ssh-ключа* 2.ssh-add \~/.ssh/id_rsa
*добавление ssh-ключа в ssh-агент* 3.clip \< \~/.ssh.id_rsa.pub *копирование
ключа в буфер обмена для добавления его в аккаунт Github*

![Создание ssh-ключа](image/03.jpg)

4.Создан репозиторий с файлом (рис. [-@fig:004]) 1.mkdir hello + echo "Hello,
World!" \> hello.html *создание файла с именем hello.html* 2.git init + git add
hello.html *создание репозитория из этого каталога и добавление файла в него*
3.git commit -m "Initial Commit" *создание коммита с названием*

![Создание репозитория](image/04.jpg)

5.Произведено фиксирование изменений в файле hello.html (рис. [-@fig:005] и
[-@fig:006]) 1.get status *проверка состояния рабочего каталога после изменений,
выдается подсказка о том, что изменения не были зафиксированы* 2.git add
hello.html *изменение файла проиндексировано и изменение еще не записано* 3.git
commit *дабавлен комментарий "added h1 tag", теперь изменение зафиксировано*

![Фиксирование изменений 1](image/05.jpg)

![Фиксирование изменений 2](image/06.jpg)

6.Получен список всех произведенных изменений, используя команду git log (рис.
[-@fig:007])

![Просмотр истории изменений](image/07.jpg)

7.Созданы теги версий (рис. [-@fig:008]) 1.git tag v1 *создание тега для текущей
версии* 2.git checkout v1\^ *переход к предыдущей версии* 3.git tag v1-beta
*создание тега для предыдущей версии*

![Теги версий](image/08.jpg)

8.Произведена отмена ненужных коммитов (рис. [-@fig:009]) 1.git add hello.html +
git commit -m "we didn't want this commit" *изменение файла и создание коммита*
2.git revert HEAD *отмена нежелательного коммита, редактирование
коммит-сообщения в редакторе*

![Отмена изменений](image/09.jpg)

9.Внесены изменения в коммит (рис. [-@fig:010]) 1.git commit --amend -m "added
personal name and email" *когда в файл добавили новые изменения к предыдущим и
нет смысла создавать новый коммит, мы его изменяем*

![Изменения в коммиты](image/10.jpg)

Выводы
======

Осуществлена работа с репозиторием, применены основные функции к ней, в
частности, связанные с управлением версиями файлов, отслеживания изменений и
переключения между ними.
