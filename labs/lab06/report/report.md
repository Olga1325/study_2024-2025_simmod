---
## Front matter
title: "Лабораторная работа №6"
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

Ознакомиться с Моделью «хищник–жертва» и выполнить соответствующие задания на эту тему.

# Выполнение лабораторной работы

Реализация модели в xcos
Зафиксируем начальные данные: a = 2, b = 1, c = 0, 3, d = 1, x(0) = 2, y(0) = 1.
В меню Моделирование, Задать переменные окружения зададим значения коэффициентов a, b, c, d(рис.[-@fig:pic1]).

![Задаю переменные окружения](image/pic1.jpeg){ #fig:pic1 width=100% }

Создаю соответствующую модель(рис.[-@fig:pic2]).

![Модель](image/pic2.jpeg){ #fig:pic2 width=100% }

Результат прпограммы - график и фазовый портрет(рис.[-@fig:pic3]), (рис.[-@fig:pic4]).

![Результат программы(график)](image/pic3.jpeg){ #fig:pic3 width=100% }

![Результат программы(фазовый портрет)](image/pic4.jpeg){ #fig:pic4 width=100% }

Реализация модели с помощью блока Modelica в xcos(рис.[-@fig:pic5]), (рис.[-@fig:pic6]).

![Параметры блока Modelica для модели](image/pic5.jpeg){ #fig:pic5 width=100% }

![Параметры блока Modelica для модели](image/pic6.jpeg){ #fig:pic6 width=100% }

Создаю соответствующую модель(рис.[-@fig:pic7]).

![Модель](image/pic7.jpeg){ #fig:pic7 width=100% }

Результат прпограммы - график и фазовый портрет(рис.[-@fig:pic8]), (рис.[-@fig:pic9]).

![Результат программы(фазовый портрет)](image/pic8.jpeg){ #fig:pic8 width=100% }

![Результат программы(график)](image/pic9.jpeg){ #fig:pic9 width=100% }

Реализую модель «хищник – жертва» в OpenModelica(рис.[-@fig:pic10]).

![Модель](image/pic10.jpeg){ #fig:pic10 width=100% }

Результат прпограммы - график и фазовый портрет(рис.[-@fig:pic11]), (рис.[-@fig:pic12]).

![Результат программы(фазовый портрет)](image/pic11.jpeg){ #fig:pic11 width=100% }

![Результат программы(график)](image/pic12.jpeg){ #fig:pic12 width=100% }

# Выводы

Ознакомилась с Моделью «хищник–жертва» и выполнила соответствующие задания на эту тему.

# Список литературы{.unnumbered}

::: {#refs}
:::
