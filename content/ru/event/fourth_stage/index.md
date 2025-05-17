---
title: Презентация и выступление по теме. Групповой проект "Рост дендритов". Этап 4. Результаты проекта. Самооценка деятельности

event: Групповой проект "Рост дендритов". Этап 4.
event_url: 

location: 
address:
  street: 
  city: 
  region: 
  postcode: 
  country: 

summary: Group project "Dendrite growth". Stage 4.
abstract: 'Мы подготовили презентацию и выступление по четвертому этапу группового проекта "Рост дендритов"'

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date: '2025-05-16T00:00:00Z'
date_end: '2025-05-16T00:00:00Z'
all_day: false

# Schedule page publish date (NOT talk date).
publishDate: '2025-05-16T00:00:00Z'

authors: [Eva Dvorkina, Angelina Chemodanova, Uliana Aleksandrova, Irina Seregina, Ivan Volgin, Yaroslav Goloschapov]
tags: []

# Is this a featured talk? (true/false)
featured: false

image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/bzdhc5b3Bxs)'
  focal_point: Right

url_code: ''
url_pdf: 'https://aachemodanova.github.io/dendrites_group_research/ru/publication/fourth_stage/report.pdf'
url_slides: 'https://aachemodanova.github.io/dendrites_group_research/ru/publication/fourth_stage/presentation.pdf'
url_video: ''

# Markdown Slides (optional).
#   Associate this talk with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides:

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects:
---

<iframe width="720" height="405" src="https://rutube.ru/play/embed/13a5c306bd983fb91f5677867104bc29/" frameBorder="0" allow="clipboard-write; autoplay" webkitAllowFullScreen mozallowfullscreen allowFullScreen></iframe>

<iframe width="560" height="315" src="https://plvideo.ru/embed/BJ6pyd44CoPW" title="Platform video player" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Актуальность

Появление дендритов играет ключевую роль в металлургии и в литейном производстве, особенно при затвердевании металлов и сплавов.

## Объект и предмет исследования: 

- Дендриты

- Кристаллические дендриты

## Цель: 

- Исследовать модель роста дендритов.

- Описать алгоритм решения задачи моделирования роста дендритов.

- Реализовать модель роста дендритов и проанализировать результаты.


## Задачи

- Рассмотреть модель роста дендритов.

- Рассмотреть алгоритм построения модели.

- Описать основные этапы алгоритма.

- Написать программу для моделирования.

- Проанализировать результаты.

![Дендритная кристаллизация после плавления внутри герметичных ампул из металлического рубидия и цезия](234.png)

# Теоретическое описание задачи. 

## Основные понятия и уравнения

### Образование дендритов

$$
S = c_p \frac{(T_m - T_\infty)}{L}\tag{1}
$$

### Уравнение теплопроводности

$$
\rho c_p \frac{\partial T}{\partial t} = \kappa \nabla^2 T \equiv \kappa \left( \frac{\partial^2 T}{\partial x^2} + \frac{\partial^2 T}{\partial y^2} \right)\tag{2}
$$

### Условие Стефана

$$
\mathbf{n} \cdot \mathbf{V} = \frac{\kappa}{\rho L} (\mathbf{n} \cdot \nabla T|_s - \mathbf{n} \cdot \nabla T|_l)\tag{3}
$$

### Условие Гиббса-Томсона  

$$
T_b = T_m \left(1 - \frac{\gamma T_m}{\rho L^2 R}\right)\tag{4}
$$

## Безразмерная температура и уравнение теплопроводности

Вводится безразмерная температура $\widetilde{T} = c_p (T - T_\infty)/L$, где $T_\infty$  — начальная температура расплава. Уравнение теплопроводности для $\widetilde{T}$ имеет вид

$$
\frac{\partial \widetilde{T}}{\partial t} = \chi \nabla^2 \widetilde{T},\tag{5}
$$

где $\chi = \kappa / \rho c_p$ — коэффициент температуропроводности.

# Описание модели

## Изменение температуры

Новое значение температуры после шага $m$ вычисляется по формуле

{{< math >}}$$
\hat{T}_{i,j} = T_{i,j} + \frac{\chi \Delta t \nabla^2 T}{m}.\tag{6}
$${{< /math >}}


### Рост дендрита 

{{< math >}}$$
T \leq \tilde{T}_m (1 + \eta_{i,j} \delta) + \lambda s_{i,j},\tag{7}
$${{< /math >}}

### Учет кривизны границы 

Кривизна границы $1/R$ приближенно вычисляется по соседям узла:

$$
1/R \approx s_{i,j} = \sum_{1} n_{i,j} + w_n \sum_{2} n_{i,j} - \left( \frac{5}{2} + \frac{5}{2} w_n \right),\tag{8}
$$

## Описание алгоритма

![Блок-схема цикла моделирования теплопроводности](teplo.png)

### Шаг 1: Задание параметров

### Шаг 2: Настройка симуляционной сетки

### Шаг 3: Расчет температурного поля

* Применение уравнения теплопроводности,
* Численная реализация уравнения

## Описание алгоритма 

![Блок-схема цикла моделирования затвердевания](zatverdevanie.png)

### Шаг 4: Моделирование роста дендритов 

Реализуется моделирование роста дендритов, основываясь на рассчитанных температурных полях и соответствующих физических законах.

## Определение фрактальной размерности

$$
N(r) \sim r^D\tag{9}
$$

где $N(r)$ — число точек внутри круга радиуса $r$.

![Фазовое и температурное поле при росте дендрита](3.png)


# Практическая часть

## Задание базовых параметров модели

```Julia
using Plots, LinearAlgebra, Statistics

# Параметры модели
N = 150          # Размер сетки (N x N)
T_initial = -1 # Начальная температура в центральной точке
steps = 200     # Количество временных шагов
dt = 1          # Шаг по времени
h = 1           # Расстояние между узлами
kappa = 0.1         # Коэффициент теплопроводности
w = 0.5         # Коэффициент для диагональных соседей
T_m = 0         # Температура плавления
$\lambda$ = 0.01         # Капиллярный радиус
$\delta$ = 0.02        # Величина флуктуаций температуры
```

## Инициализация сетки
    
```Julia
# Инициализация сетки
T = zeros(N, N)            # Матрица температур
n = zeros(Int, N, N)       # Матрица состояний (0 - жидкое, 1 - твердое)
T[N÷2+1, N÷2+1] = T_initial  # Установка начальной температуры в центральной точке
n[N÷2+1, N÷2+1] = 1
```

## Базовые функции

  - Метод полиномиальной аппроксимации
  - Среднее значение температуры
  - Кривизна границы
  - Количества затвердевших частиц 
  - Среднеквадратичный радиус 

![Функция curvate](func.png)

## Модель теплопроводности

![Распределение температуры без шума](8.png)

Функция `simulate_heat_conduction` на основе уравнения обновления температуры:

![Функция simulate_heat_conduction](s.png)

## Добавление процесса затвердевания

Реализована функция `simulate_solidification`, которая выполняет следующие шаги:

1. Обновление температур
2. Проверка условия затвердевания
3. Обновление состояний

![Фрагмент функции simulate_solidification](f.png)

## Результаты моделирования. Исследование влияния капиллярного радиуса

![Исследование влияния начального переохлаждения и величины капиллярного радиуса](11.png)

## Динамика роста агрегата

![Зависимость числа затвердевших частиц от времени](14.png)

![Зависимость среднеквадратического радиуса от времени](15.png)

## Фрактальная размерность

![Зависимость фрактальной размерности от времени](6.png)

Фрактальную размерность $D$ можно определить через логарифмическую регрессию:

$$ 
D = \frac{\log N(r)}{\log r} 
\tag{10}
$$

где:

- $N(r)$ - количество частиц внутри радиуса $r$
- $D$ - искомая фрактальная размерность

Реализована функция `fractal_dimension`

## Влияние теплового шума

![Значение теплового шума ($\delta$) 0.01](18.png)

![Значение теплового шума ($\delta$) 0.05](19.png)

![Значение теплового шума ($\delta$) 0.1](20.png)

# Выводы

Во время выполнения группового проекта мы:

- сделали теоретическое описание модели роста дендритов и определили задачи дальнейшего исследования,

- описали процесс создания алгоритма для моделирования роста дендритов, включающий все ключевые этапы

- смоделировали процесс теплопроводности.

- исследовали влияние начального переохлаждения и капиллярного радиуса на форму дендритов,

- проанализировали динамика роста агрегата и его фрактальная размерность,

- изучили влияние теплового шума на морфологию агрегатов.
