---
title: Презентация и выступление по теме. Групповой проект "Рост дендритов". Этап 2. Описание алгоритма решения задачи

event: Групповой проект "Рост дендритов". Этап 2.
event_url: 

location: 
address:
  street: 
  city: 
  region: 
  postcode: 
  country: 

summary: Group project "Dendrite growth". Stage 2.
abstract: 'Мы подготовили презентацию и выступление по второму этапу группового проекта "Рост дендритов"'

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date: '2025-04-05T00:00:00Z'
date_end: '2025-04-05T00:00:00Z'
all_day: false

# Schedule page publish date (NOT talk date).
publishDate: '2025-03-21T00:00:00Z'

authors: [Eva Dvorkina, Angelina Chemodanova, Uliana Aleksandrova, Irina Seregina, Ivan Volgin, Yaroslav Goloschapov]
tags: []

# Is this a featured talk? (true/false)
featured: false

image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/bzdhc5b3Bxs)'
  focal_point: Right

url_code: ''
url_pdf: 'https://aachemodanova.github.io/dendrites_group_research/ru/publication/second_stage/report.pdf'
url_slides: 'https://aachemodanova.github.io/dendrites_group_research/ru/publication/second_stage/presentation.pdf'
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

<iframe width="720" height="405" src="https://rutube.ru/play/embed/288b97aa715fe1c975df9768e0ca6921/" frameBorder="0" allow="clipboard-write; autoplay" webkitAllowFullScreen mozallowfullscreen allowFullScreen></iframe>

<iframe width="720" height="405" src="https://plvideo.ru/embed/eDSYh8m2shu5" title="Platform video player" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Актуальность

Появление дендритов играет ключевую роль в металлургии и литейном производстве, особенно при затвердевании металлов и сплавов, поскольку микроструктура образующихся дендритов во многом определяет механические, электрические и термические свойства получаемых материалов. Изучение их характеристик важно не только для теоретического понимания процессов кристаллизации, но и для практики, для совершенствования технологий производства современных материалов с заданными свойствами. 
Таким образом, на втором этапе группового проекта описывается алгоритм решения задачи моделирования кристаллизации. 

**Алгоритм** - систематизированная последовательность действий, необходимых для достижения поставленной цели. В контексте научных исследований алгоритмы важны не только для повышения эффективности вычислений, но и для обеспечения воспроизводимости результатов, что является фундаментальным требованием научного метода.

## Объект и предмет исследования
- Дендриты, 
- Кристаллические дендриты

## Цели

Описать алгоритм решения задачи моделирования роста дендритов.

## Задачи

- Рассмотреть алгоритм построения модели роста дендритов.
- Описать основные этапы алгоритма

## Определение

Дендрит - это кристалл, который развивается с типичной формой разветвления, напоминающей фрактал.  В металлах они образуются в процессе кристаллизации из переохлажденного расплава.

# Алгоритм

## Шаг 1: Задание параметров
- Физические свойства вещества
- Начальные условия

## Шаг 2: Настройка симуляционной сетки

- Создание симуляционной сетки.
- Инициализация затравки.

## Шаг 3: Расчет температурного поля

- Применение уравнения теплопроводности
- Вычислить новое распределение температуры на каждом шаге времени {{< math >}}$\Delta t${{< /math >}}
- Обновлять значения температуры в каждой точке сетки
- Повторять вычисления до достижения стационарного состояния или заданного времени.

## Шаг 4: Моделирование роста дендритов

- Критерий затвердевания
- Использование условия Стефана
- Применение условия Гиббса-Томсона
- Обновление параметров
- Определение фрактальной размерности

![Фазовое и температурное поле при росте дендрита](3.png)

## Шаг 5: Анализ структуры дендритов
- Морфологический анализ
- Корреляционный анализ
- Исследование влияния теплового шума {{< math >}}$\delta${{< /math >}}

## Шаг 6: Визуализация процесса

![Симуляция роста дендрита](8.png)


## Выводы
Завершен второй этап группового проекта по теме "Рост дендритов", в результате  был описан процесс создания алгоритма для моделирования роста дендритов, включающий все ключевые этапы: от задания начальных параметров и настройки расчетной сетки до моделирования процесса роста и детального анализа полученных структур. 

