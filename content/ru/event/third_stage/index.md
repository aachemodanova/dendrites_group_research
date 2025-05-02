---
title: Презентация и выступление по теме. Групповой проект "Рост дендритов". Этап 3. Описание программной реализации

event: Групповой проект "Рост дендритов". Этап 3.
event_url: 

location: 
address:
  street: 
  city: 
  region: 
  postcode: 
  country: 

summary: Group project "Dendrite growth". Stage 3.
abstract: 'Мы подготовили презентацию и выступление по третьему этапу группового проекта "Рост дендритов"'

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date: '2025-05-02T00:00:00Z'
date_end: '2025-05-02T00:00:00Z'
all_day: false

# Schedule page publish date (NOT talk date).
publishDate: '2025-05-02T00:00:00Z'

authors: [Eva Dvorkina, Angelina Chemodanova, Uliana Aleksandrova, Irina Seregina, Ivan Volgin, Yaroslav Goloschapov]
tags: []

# Is this a featured talk? (true/false)
featured: false

image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/bzdhc5b3Bxs)'
  focal_point: Right

url_code: ''
url_pdf: 'https://aachemodanova.github.io/dendrites_group_research/ru/publication/third_stage/report.pdf'
url_slides: 'https://aachemodanova.github.io/dendrites_group_research/ru/publication/third_stage/presentation.pdf'
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

<iframe width="720" height="405" src="https://rutube.ru/play/embed/8d17b15b60b0f12d8fa4222d2860cc9d/" frameBorder="0" allow="clipboard-write; autoplay" webkitAllowFullScreen mozallowfullscreen allowFullScreen></iframe>

<iframe width="560" height="315" src="https://plvideo.ru/embed/Pdk1XiznJ3qf" title="Platform video player" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Актуальность

Появление дендритов играет ключевую роль в металлургии и литейном производстве, особенно при затвердевании металлов и сплавов, поскольку микроструктура образующихся дендритов во многом определяет механические, электрические и термические свойства получаемых материалов. Изучение их характеристик важно не только для теоретического понимания процессов кристаллизации, но и для практики, для совершенствования технологий производства современных материалов с заданными свойствами.

## Объект и предмет исследования

- Дендриты, 
- Кристаллические дендриты

## Цели и задачи

1. Написать программу, моделирующую теплопроводность. Задать начальную температуру равную нулю во всех точках, кроме центральной и пронаблюдать, как изменятся распределения температуры со временем.
2. Добавить в модель процесс затвердевания. Изучить, как начальное переохлаждение и капиллярный радиус влияют на форму образующихся дендритов.
3. Исследовать, как со временем изменяются количество частиц в агрегате и его среднеквадратичный радиус в различных режимах.
4. Определить фрактальную размерность полученных структур
5. Проанализировать, как величина теплового шума влияет на морфологию формирующихся агрегатов.


# Выполнение задач третьего этапа

## Задание базовых параметров моделирования

```Julia
N = 150          # Размер сетки (N x N)
T_initial = -1 # Начальная температура в центральной точке
steps = 200     # Количество временных шагов
dt = 1          # Шаг по времени
h = 1           # Расстояние между узлами
kappa = 0.1         # Коэффициент теплопроводности
w = 0.5         # Коэффициент для диагональных соседей
T_m = 0         # Температура плавления
lambda = 0.01         # Капиллярный радиус
delta = 0.02        # Величина флуктуаций температуры
```

## Инициализация сетки

```Julia
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

![Функция average_temperature](b.PNG)

## Базовые функции

  - Метод полиномиальной аппроксимации
  - Среднее значение температуры
  - Кривизна границы
  - Количества затвердевших частиц 
  - Среднеквадратичный радиус 

![Функция curvate](func.png)

## Базовые функции

  - Метод полиномиальной аппроксимации
  - Среднее значение температуры
  - Кривизна границы
  - Количества затвердевших частиц 
  - Среднеквадратичный радиус 
  
![Функции count_solid_particles и mean_squared_radius](c.PNG)

## Модель теплопроводности

![Распределение температуры без шума](1.png)

Функция `simulate_heat_conduction` на основе уравнения обновления температуры:

![Функция simulate_heat_conduction](s.png)

## Добавление процесса затвердевания

Реализована функция `simulate_solidification`, которая выполняет следующие шаги:

1. Обновление температур
2. Проверка условия затвердевания
3. Обновление состояний

![Фрагмент функции simulate_solidification](f.png)

## Результаты моделирования. Исследование влияния капиллярного радиуса

![Исследование влияния начального переохлаждения и величины капиллярного радиуса](4.png)

## Динамика роста агрегата

![Зависимость числа затвердевших частиц от времени](7.png)

![Зависимость среднеквадратического радиуса от времени](8.png)

## Фрактальная размерность

![Зависимость фрактальной размерности от времени](9.png)

Фрактальную размерность $D$ можно определить через логарифмическую регрессию:

$$ 
D = \frac{\log N(r)}{\log r} 
$$

где:

- $N(r)$ - количество частиц внутри радиуса $r$
- $D$ - искомая фрактальная размерность

Реализована функция `fractal_dimension`

## Влияние теплового шума

![Значение теплового шума ($\delta$) 0.01](11.png)

![Значение теплового шума ($\delta$) 0.05](12.png)

![Значение теплового шума ($\delta$) 0.1](13.png)
## Выводы

1. Смоделирован процесс теплопроводности.
2. Исследовано влияние начального переохлаждения и капиллярного радиуса на форму дендритов.
3. Проанализирована динамика роста агрегата и его фрактальная размерность.
4. Изучено влияние теплового шума на морфологию агрегатов.

Результаты показывают, что:

- Тепловой шум значительно влияет на структуру дендритов, увеличивая их нерегулярность и скорость роста.

