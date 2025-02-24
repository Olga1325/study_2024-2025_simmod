---
## Front matter
title: "Лабораторная работа №4"
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

Самостоятельно выполнить задания из лабораторной работы.

# Задание

– сеть состоит из N TCP-источников, N TCP-приёмников, двух маршрутизаторов
R1 и R2 между источниками и приёмниками (N — не менее 20);
– между TCP-источниками и первым маршрутизатором установлены дуплексные
соединения с пропускной способностью 100 Мбит/с и задержкой 20 мс очередью
типа DropTail;
– между TCP-приёмниками и вторым маршрутизатором установлены дуплексные
соединения с пропускной способностью 100 Мбит/с и задержкой 20 мс очередью
типа DropTail;
– между маршрутизаторами установлено симплексное соединение (R1–R2) с про-
пускной способностью 20 Мбит/с и задержкой 15 мс очередью типа RED,
размером буфера 300 пакетов; в обратную сторону — симплексное соедине-
ние (R2–R1) с пропускной способностью 15 Мбит/с и задержкой 20 мс очередью
типа DropTail;
– данные передаются по протоколу FTP поверх TCPReno;
– параметры алгоритма RED: qmin = 75, qmax = 150, qw = 0, 002, pmax = 0.1;
– максимальный размер TCP-окна 32; размер передаваемого пакета 500 байт; время
моделирования — не менее 20 единиц модельного времени.

# Выполнение лабораторной работы

Создаю файл lab04.tcl. Пишу код для выполнения задания(рис.1[-@fig:pic1]), (рис.2[-@fig:pic2]).

![Заполнение файла](image/pic1.jpeg){ #fig:pic1 width=100% }

![Заполнение файла](image/pic2.jpeg){ #fig:pic2 width=100% }

Получились следующие графики(рис.1[-@fig:pic3]), (рис.2[-@fig:pic4]), (рис.2[-@fig:pic5]). (рис.2[-@fig:pic6]), (рис.2[-@fig:pic7]).

![Результат программы](image/pic3.jpeg){ #fig:pic3 width=100% }

![Изменение размера окна TCP на линке 1-го источника ](image/pic4.jpeg){ #fig:pic4 width=100% }

![зменение размера средней длины очереди на линке](image/pic5.jpeg){ #fig:pic5 width=100% }

![Изменение размера окна TCP на всех источниках ](image/pic6.jpeg){ #fig:pic6 width=100% }

![Изменение размера длины очереди на линке](image/pic7.jpeg){ #fig:pic7 width=100% }

Создаю файл graph_plot_lab04 и заполняю его(рис.2[-@fig:pic8]).

![Заполнение файла](image/pic8.jpeg){ #fig:pic8 width=100% }

Даю права файлу и запускаю его(рис.2[-@fig:pic9]).

![Заполнение файла](image/pic9.jpeg){ #fig:pic9 width=100% }

Получились следующие графики(рис.1[-@fig:pic10]), (рис.2[-@fig:pic11]), (рис.2[-@fig:pic12]). (рис.2[-@fig:pic13]).

![Изменение размера окна TCP на линке 1-го источника](image/pic10.jpeg){ #fig:pic10 width=100% }

![Изменение размера окна TCP на всех источниках](image/pic11.jpeg){ #fig:pic11 width=100% }

![Изменение размера длины очереди на линке](image/pic12.jpeg){ #fig:pic12 width=100% }

![Изменение размера длины очереди на линке](image/pic13.jpeg){ #fig:pic13 width=100% }

# Выводы

Выполнила самостоятельную работу.

# Список литературы{.unnumbered}

::: {#refs}
:::
