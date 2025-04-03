---
## Front matter
title: "Лабораторная работа №9"
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

Ознакомиться с Моделью «Накорми студентов».
Рассмотрим пример студентов, обедающих пирогами. Голодный студент стано-
вится сытым после того, как съедает пирог.

# Выполнение лабораторной работы

Рассмотрим пример студентов, обедающих пирогами. Голодный студент стано-
вится сытым после того, как съедает пирог.
Таким образом, имеем:
– два типа фишек: «пироги» и «студенты»;
– три позиции: «голодный студент», «пирожки», «сытый студент»;
– один переход: «съесть пирожок».
 Рисуем граф сети. Для этого с помощью контекстного меню создаём новую сеть, добавляем позиции, переход и дуги(рис.[-@fig:pic1]).

![Граф сети модели «Накорми студентов»](image/pic1.jpeg){ #fig:pic1 width=100% }

В меню задаём новые декларации модели: типы фишек, начальные значения
позиций, выражения для дуг. Для этого наведя мышку на меню Standart declarations,
правой кнопкой вызываем контекстное меню и выбираем New Decl. После этого задаем тип s фишкам, относящимся к студентам, тип p — фишкам, относящимся к пирогам, задаём значения переменных x и y для дуг и начальные значения мультимножеств init_stud и init_food(рис.[-@fig:pic2]).

![Декларации модели «Накорми студентов»](image/pic2.jpeg){ #fig:pic2 width=100% }

Запускаем нашу модель(рис.[-@fig:pic3]).

![Запуск модели «Накорми студентов»](image/pic3.jpeg){ #fig:pic3 width=100% }

Вычисляю пространство состояний. Формирую отчёт о пространстве состояний и анализирую его. Строю граф пространства состояний(рис.[-@fig:pic4]), (рис.[-@fig:pic5]), (рис.[-@fig:pic6]).

![Отчет модели «Накорми студентов»](image/pic4.jpeg){ #fig:pic4 width=100% }

![Граф модели «Накорми студентов»](image/pic5.jpeg){ #fig:pic5 width=100% }

![Анализ отчета модели «Накорми студентов»](image/pic6.jpeg){ #fig:pic6 width=100% }

# Выводы

Ознакомилась с Моделью «Накорми студентов».
Рассмотрела пример студентов, обедающих пирогами. Голодный студент стано-
вится сытым после того, как съедает пирог.

# Список литературы{.unnumbered}

::: {#refs}
:::
