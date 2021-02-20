---
# Front matter
lang: ru-RU
title: "Математическое моделирование"
subtitle: "Лабораторная работа №2"
author: "Соколова Анастасия Витальевна"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Цель данной лабораторной работы --- построение математической модели на примере
задачи о погоне для выбора правильной стратегии при решении задач поиска.

# Задание

-   Постановка задачи

-   Вывод дифференциальных уравнений для 2 случаев

-   Решение системы 2 дифференциальных уравнений

-   Построение траектории движения катера и лодки

# Выполнение лабораторной работы

1. Определение начальных значений.
   - t0=0 - начальный момент времени
   - xл0=0 - положение лодки
   - xк0=k, k=20км - положение катера
   - v - скорость лодки
   - 5v - скорость катера

2. Ввод полярных координат. (рис. [-@fig:001])
   - tetha = xл0 = 0
   - полярная ось r проходит через точку нахождения катера береговой охраны

![Положение катера и лодки в начальный момент времени](image/01.jpg)

3. Нахождение расстояния, которое катер должен двигаться прямолинейно, чтобы 
после оказаться на одном расстоянии от полюса, что и лодка.
   - x - расстояние, после которого катер начнет двигаться вокруг полюса
   - t - время, за которое катер и лодка окажутся на одном расстоянии от полюса
   - лодка: расстояние - x
   - катер: расстояние - k-x (1 случай), k+x (2 случай)
   - t=x/v - время лодки
   - t=k-x/5v ; t=k+x/5v - время катера

   1. x/v=k-x/5v; x=k-x/5; 5x=k-x; 6x=k; x = k/6  x1=k/6
   2. x/v=k+x/5v; x=k+x/5; 5x=k+x; 4x=k; x=k/4    x2=k/4

4. Разложение скорости катера на тангенциальную и радиальную состовляющие, так
как после прохождения расстояния x катер будет двигаться вокруг полюса. (рис. [-@fig:002])
   - vr=dr/dt=v - радиальная скорость
   - vt=(dtetha/dt)*r - тангенциальная
   - vt=sqrt(25v^2-v^2)=sqrt(24)*v - по рисунку
   - r*(dtetha/dt)=sqrt(24)*v - приравнивание двух равенств

![Разложение скорости катера](image/02.jpg)

5. Решение системы уравнений для двух случаев: tetha0=0, r0=x1 и tetha0=-pi, r0=x2.
   - dr/dt=v  dt=dr/v
   - r*(dtetha/dt)=sqrt(24)*v dt=(rdtetha)/(sqrt(24)*v)
   - dr=(1/sqrt(24))*r*dtetha
   - dr/dtetha=r/sqrt(24) - получение траектории движения катера в полярных координатах

6. Написание программы в scilab.
	s=20; //начальное расстояние от лодки до катера
	fi=3*%pi/4;
	
	//функция, описывающая движение катера
	function dr=f(tetha,r)
  	dr=r/sqrt(24);
	endfunction;
	
	//начальные условия - случай 1
	//r0=s/6;
	//tetha0=0;
	
	//начальные условия - случай 2
	r0=s/4;
	tetha0=-%pi;
	
	tetha=0:0.01:2*%pi;
	r=ode(r0,tetha0,tetha,f);
	
	//функция, описывающая движение лодки
	function xt=f2(t)
  	xt=tan(fi)*t;
	endfunction;
	
	t=0:1:50;
	
	//построение траектории движения катера в полярных координатах
	polarplot(tetha,r,style=color('green'));
	//лодка
	plot2d(t,f2(t),style=color('red'));

7. Построение траекторий движения катера и лодки и определение точки пересечения их траекторий.
   - 1 случай: r=10, tetha=3pi/4=45  x=7.07 y=7.07 (рис. [-@fig:003])
   - 2 случай: r=30, tetha=3pi/4=45  x=21.21 y=21.21 (рис. [-@fig:004])

![Траектории лодки и катера в 1 случае](image/03.jpg)

![Траектории лодки и катера в 2 случае](image/04.jpg)

# Выводы

Построена математическая модель задачи о погоне с приведеним рассуждений и выводом дифференциальных построений
с дальнейшим построением траектории движения катера и лодки для двух случаев.
