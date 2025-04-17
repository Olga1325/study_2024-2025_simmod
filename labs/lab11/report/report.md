---
## Front matter
title: "Лабораторная работа №11"
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

Научиться работать с Моделью системы массового обслуживания M |M |1

# Выполнение лабораторной работы

В систему поступает поток заявок двух типов, распределённый по пуассоновскому
закону. Заявки поступают в очередь сервера на обработку. Дисциплина очереди -
FIFO. Если сервер находится в режиме ожидания (нет заявок на сервере), то заявка
поступает на обработку сервером.

Будем использовать три отдельных листа: на первом листе опишем граф системы
(рис. 11.1), на втором — генератор заявок (рис. 11.2), на третьем — сервер обработки
заявок (рис. 11.3).
1.1. Сеть имеет 2 позиции (очередь — Queue, обслуженные заявки — Complited)
и два перехода (генерировать заявку — Arrivals, передать заявку на обработку сер-
веру — Server). Переходы имеют сложную иерархическую структуру, задаваемую
на отдельных листах модели (с помощью соответствующего инструмента меню —
Hierarchy)(рис.[-@fig:pic1]).

![Граф сети системы обработки заявок в очереди](image/pic1.jpeg){ #fig:pic1 width=100% }

раф генератора заявок имеет 3 позиции (текущая заявка — Init, следующая
заявка — Next, очередь — Queue из листа System) и 2 перехода (Init — определяет
распределение поступления заявок по экспоненциальному закону с интенсивностью
100 заявок в единицу времени, Arrive — определяет поступление заявок в очередь)(рис.[-@fig:pic2]).

![Граф генератора заявок системы](image/pic2.jpeg){ #fig:pic2 width=100% }

Граф процесса обработки заявок на сервере имеет 4 позиции (Busy — сервер
занят, Idle — сервер в режиме ожидания, Queue и Complited из листа System) и 2
перехода (Start — начать обработку заявки, Stop — закончить обработку заявки)(рис.[-@fig:pic3]).

![Граф процесса обработки заявок на сервере системы](image/pic3.jpeg){ #fig:pic3 width=100% }

Зададим декларации системы.
Определим множества цветов системы (colorset):
– фишки типа UNIT определяют моменты времени;
– фишки типа INT определяют моменты поступления заявок в систему.
– фишки типа JobType определяют 2 типа заявок — A и B;
– кортеж Job имеет 2 поля: jobType определяет тип работы (соответственно име-
ет тип JobType, поле AT имеет тип INT и используется для хранения времени
нахождения заявки в системе;
– фишки Jobs — список заявок;
– фишки типа ServerxJob — определяют состояние сервера, занятого обработкой
заявок(рис.[-@fig:pic4]).

![Декларации системы](image/pic4.jpeg){ #fig:pic4 width=100% }

Переменные модели:
– proctime — определяет время обработки заявки;
– job — определяет тип заявки;
– jobs — определяет поступление заявок в очередь(рис.[-@fig:pic5]).

![Декларации системы](image/pic5.jpeg){ #fig:pic5 width=100% }

Определим функции системы:
– функция expTime описывает генерацию целочисленных значений через интерва-
лы времени, распределённые по экспоненциальному закону;
– функция intTime преобразует текущее модельное время в целое число;
– функция newJob возвращает значение из набора Job — случайный выбор типа
заявки (A или B)(рис.[-@fig:pic6]), (рис.[-@fig:pic7]), (рис.[-@fig:pic8]), (рис.[-@fig:pic9]).

![Декларации системы](image/pic6.jpeg){ #fig:pic6 width=100% }

![Декларации системы](image/pic7.jpeg){ #fig:pic7 width=100% }

![Декларации системы](image/pic8.jpeg){ #fig:pic8 width=100% }

![Декларации системы](image/pic9.jpeg){ #fig:pic9 width=100% }

Зададим параметры модели на графах сети. – у позиции Queue множество цветов фишек — Jobs; начальная маркировка 1`[]
определяет, что изначально очередь пуста.
– у позиции Completed множество цветов фишек — Job(рис.[-@fig:pic10]).

![Параметры элементов основного графа системы обработки заявок в очереди](image/pic10.jpeg){ #fig:pic10 width=100% }

На листе Arrivals:
– у позиции Init: множество цветов фишек — UNIT; начальная маркировка 1`()@0
определяет, что поступление заявок в систему начинается с нулевого момента
времени;
– у позиции Next: множество цветов фишек — UNIT;
– на дуге от позиции Init к переходу Init выражение () задаёт генерацию заявок;
– на дуге от переходов Init и Arrive к позиции Next выражение
()@+expTime(100) задаёт экспоненциальное распределение времени между
поступлениями заявок;
– на дуге от позиции Next к переходу Arrive выражение () задаёт перемещение
фишки;
– на дуге от перехода Arrive к позиции Queue выражение jobs^^[job] задает
поступление заявки в очередь;
– на дуге от позиции Queue к переходу Arrive выражение jobs задаёт обратную
связь(рис.[-@fig:pic11]).

![Параметры элементов генератора заявок системы](image/pic11.jpeg){ #fig:pic11 width=100% }

На листе Server:
– у позиции Busy: множество цветов фишек — Server, начальное значение мар-
кировки — 1`server@0 определяет, что изначально на сервере нет заявок на
обслуживание;
– у позиции Idle: множество цветов фишек — ServerxJob;
– переход Start имеет сегмент кода
output (proctime); action expTime(90); определяющий, что время об-
служивания заявки распределено по экспоненциальному закону со средним
временем обработки в 90 единиц времени;
– на дуге от позиции Queue к переходу Start выражение job::jobs определяет,
что сервер может начать обработку заявки, если в очереди есть хотя бы одна
заявка;
– на дуге от перехода Start к позиции Busy выражение
(server,job)@+proctime запускает функцию расчёта времени обработки заяв-
ки на сервере;
– на дуге от позиции Busy к переходу Stop выражение (server,job) говорит
о завершении обработки заявки на сервере;
– на дуге от перехода Stop к позиции Completed выражение job показывает, что
заявка считается обслуженной;
– выражение server на дугах от и к позиции Idle определяет изменение состояние
сервера (обрабатывает заявки или ожидает);
– на дуге от перехода Start к позиции Queue выражение jobs задаёт обратную
связь(рис.[-@fig:pic12]).

![Параметры элементов обработчика заявок системы](image/pic12.jpeg){ #fig:pic12 width=100% }

Запуск модели(рис.[-@fig:pic13]),(рис.[-@fig:pic14]).

![Запуск модели](image/pic13.jpeg){ #fig:pic13 width=100% }

![Запуск модели](image/pic14.jpeg){ #fig:pic14 width=100% }

# Выводы

Научилась работать с Моделью системы массового обслуживания M |M |1

# Список литературы{.unnumbered}

::: {#refs}
:::
