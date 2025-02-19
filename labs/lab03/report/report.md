---
## Front matter
title: "Лабораторная работа №3"
subtitle: "Дисциплина: Имитационное моделирование"
author: "Пронякова Ольга Максимовна"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Провести моделирование системы массового обслуживания.

# Задание

Реализация модели на NS-2

График в GNUplot

# Выполнение лабораторной работы

Реализация модели на NS-2рис. выполнение кода из инструкции([-@fig:pic1]), ([-@fig:pic2]).

![Код](image/pic1.jpeg){ #fig:pic1 width=100% }

![результат выполнение программы](image/pic2.jpeg){ #fig:pic2 width=100% }

В каталоге с проектом создаю отдельный файл graph_plot:
touch graph_plot
Открываю его на редактирование и добавляю следующий код, обращая внимание
на синтаксис GNUplot([-@fig:pic3]).

![редактирование файла](image/pic3.jpeg){ #fig:pic3 width=100% }

Сделала файл исполняемым. После компиляции файла с проектом, запускаю скрипт в созданном файле graph_plot, который создаст файл qm.pdf с результатами моделирования([-@fig:pic4]), ([-@fig:pic5]).

![Делаю файл исполняемым и запускаю его](image/pic4.jpeg){ #fig:pic4 width=100% }

![результат выполнение программы](image/pic5.jpeg){ #fig:pic5 width=100% }

# Выводы

Провела моделирование системы массового обслуживания.

# Список литературы{.unnumbered}

::: {#refs}
:::
