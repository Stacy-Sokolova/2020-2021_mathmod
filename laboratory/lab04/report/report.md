---
# Front matter
lang: ru-RU
title: "Отчет по лабораторной работе №4"
subtitle: "Модель гармонических колебаний. Вариант 33"
author: "Соколова Анастасия Витальевна НФИбд-03-18"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
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
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the υalue makes tex try to haυe fewer lines in the paragraph.
  - \interlinepenalty=0 # υalue of the penalty (node) added after each line of a paragraph.
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

Рассмотреть линейный гармонический осциллятор, модель гармонических колебаний


# Задание

1. Построить решение уравнения гармонического осциллятора без затухания
2. Записать уравнение свободных колебаний гармонического осциллятора с
затуханием, построить его решение
3. Построить фазовый портрет гармонических колебаний с затуханием
4. Записать уравнение колебаний гармонического осциллятора, если на систему
действует внешняя сила, построить его решение
5. Построить фазовый портрет колебаний с действием внешней силы


# Выполнение лабораторной работы


## Условие задачи

Постройте фазовый портрет гармонического осциллятора и решение уравнения
гармонического осциллятора для следующих случаев
1. Колебания гармонического осциллятора без затуханий и без действий внешней
силы $$\ddot{x}+1.7x=0$$
2. Колебания гармонического осциллятора c затуханием и без действий внешней
силы $$\ddot{x}+9.8\dot{x}+x=0$$
3. Колебания гармонического осциллятора c затуханием и под действием внешней
силы $$\ddot{x}+3.9\dot{x}+2.9x=0.9cos(2t)$$
На интервале t=[0;29] (шаг 0.05) с начальными условиями [0,-1.4].

## Теоретическое введение

Уравнение свободных колебаний гармонического осциллятора имеет
следующий вид: $$\ddot{x}+2g\dot{x}+w^2x=f(t)$$, где x – переменная, описывающая состояние системы 
(смещение грузика, заряд конденсатора и т.д.), g – параметр, характеризующий потери энергии (трение в 
механической системе, сопротивление в контуре), w – собственная частота колебаний, t – время.

Для однозначной разрешимости уравнения второго порядка необходимо
задать два начальных условия вида
$$\[
  \begin{cases}
    x(t_0)=x_0       \\
    \dot{x}(t_0)=y_0 
  \end{cases}
\]$$

Уравнение второго порядка можно представить в виде системы двух уравнений первого порядка:
$$\[
  \begin{cases}
    \dot{x}=y      \\
     \dot{y}=-w_0^2x-gy-f(t)
  \end{cases}
\]$$

Тогда начальные условия для системы примут вид:
$$\[
  \begin{cases}
    x(t_0)=x_0       \\
    y(t_0)=y_0 
  \end{cases}
\]$$

Значение фазовых координат x, y в любой момент времени полностью 
определяет состояние системы. Решению уравнения движения как функции
времени отвечает гладкая кривая в фазовой плоскости. Она называется фазовой
траекторией. Если множество различных решений (соответствующих различным 
начальным условиям) изобразить на одной фазовой плоскости, возникает общая
картина поведения системы. Такую картину, образованную набором фазовых
траекторий, называют фазовым портретом.

## Решение

1. Колебания гармонического осциллятора без затуханий и без действий внешней
силы: $$\ddot{x}+1.7x=0$$ (рис. [-@fig:001])
Уравнение в виде системы двух уравнений первого порядка:
$$\[
  \begin{cases}
    \dot{x}=y      \\
     \dot{y}=-1.7x
  \end{cases}
\]$$

![Фазовый портрет гармонического осциллятора без затуханий, без
действия внешней силы](image/01.jpg)


2. Колебания гармонического осциллятора c затуханием и без действий внешней
силы: $$\ddot{x}+9.8\dot{x}+x=0$$ (рис. [-@fig:002])
Уравнение в виде системы двух уравнений первого порядка:
$$\[
  \begin{cases}
    \dot{x}=y      \\
     \dot{y}=-x-9.8y
  \end{cases}
\]$$

![Фазовый портрет гармонического осциллятора c затуханием, без действий внешней
силы](image/02.jpg)


3. Колебания гармонического осциллятора c затуханием и под действием внешней
силы: $$\ddot{x}+3.9\dot{x}+2.9x=0.9cos(2t)$$ (рис. [-@fig:003])
Уравнение в виде системы двух уравнений первого порядка:
$$\[
  \begin{cases}
    \dot{x}=y      \\
     \dot{y}=-2.9x-3.9y-0.9cos(2t)
  \end{cases}
\]$$

![Фазовый портрет гармонического осциллятора c затуханием, под действием внешней
силы](image/03.jpg)


4. 
*Код в среде python*
```python
    import numpy as np
    from scipy.integrate import odeint
    import matplotlib.pyplot as plt
    
    g = 9.8
    w = 1.0 #w^2

    def f(t):
        return 0.0*t

    def dx(x, t):
        return np.array([x[1], -w*x[0]-g*x[1]-f(t)])

    t = np.linspace(0, 29, 600)
    x0 = np.array([0, -1.4])

    x = odeint(dx, x0, t)

    plt.plot(x[:, 0], x[:, 1])
    plt.xlabel("x")
    plt.ylabel("y")
    plt.grid()
    plt.show()
```


# Выводы

- Рассмотрели модель гармонических колебаний
- Построили решение уравнения гармонического осциллятора при различных условиях
- И построили фазовый портрет гармонических колебаний