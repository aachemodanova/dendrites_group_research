---
title: 'Group project "Dendrite growth". Stage 1: The scientific problem of the project'

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - Eva Dvorkina
  - Angelina Chemodanova
  - Uliana Aleksandrova
  - Irina Seregina
  - Ivan Volgin
  - Yaroslav Goloschapov

# Author notes (optional)
author_notes:

date: '2025-03-01T00:00:00Z'
doi: ''

# Schedule page publish date (NOT publication's date).
publishDate: '2025-03-01T00:00:00Z'

# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.
publication_types: ['project_stages']

abstract: Our research group is working on a project on "Dendrite growth," in which we explore a mathematical model of this process. 


# Summary. An optional shortened abstract.
summary: Our research group is working on a project on "Dendrite growth," in which we explore a mathematical model of this process.

tags: []

# Display this page in the Featured widget?
featured: true

# Custom links (uncomment lines below)
links:
  - name: report_md
    url: https://github.com/evdvorkina/study_2024-2025_mathmod/blob/master/project-group/stage1/report/report.md
  - name: report_pdf
    url: https://github.com/evdvorkina/study_2024-2025_mathmod/blob/master/project-group/stage1/report/report.pdf
  - name: report_docx
    url: https://github.com/evdvorkina/study_2024-2025_mathmod/blob/master/project-group/stage1/report/report.docx
  - name: presentation_md
    url: https://github.com/evdvorkina/study_2024-2025_mathmod/blob/master/project-group/stage1/presentation/presentation.md
  - name: presentation_pdf
    url: https://github.com/evdvorkina/study_2024-2025_mathmod/blob/master/project-group/stage1/presentation/presentation.pdf
  - name: presentation_html
    url: https://github.com/evdvorkina/study_2024-2025_mathmod/blob/master/project-group/stage1/presentation/presentation.html
  - name: rutube
    url: https://plvideo.ru/watch?v=vIeydVQu--Je&list=LIYh9zr7Zwte
  - name: plvideo
    url: https://plvideo.ru/watch?v=vIeydVQu--Je&list=LIYh9zr7Zwte

url_pdf: ''
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/pLCdAaMFLTE)'
  focal_point: ''
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects:
  - example

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: presentation.md
---

{{% callout note %}}
# Информация
{{% /callout %}}

{{% callout note %}}
## Состав исследовательской группы

- Дворкина Е. В.
- Чемоданова А. А.
- Серёгина И. А.
- Волгин И. А.
- Александрова У. В.
- Голощапов Я. В.
{{% /callout %}}

{{% callout note %}}
# Вводная часть
{{% /callout %}}

{{% callout note %}}
## Актуальность

  - Ключевая роль в металлургии и литейном производстве.
  - теоретическое понимание процессов кристаллизации,
  - улучшение технологий производства материалов.
{{% /callout %}}

{{% callout note %}}
## Объект и предмет исследования

  - Дендриты
  - Кристаллические дендриты
{{% /callout %}}

{{% callout note %}}
## Цели и задачи
Цели: 

- Исследовать модель роста дендритов

Задачи:

- Рассмотреть комбинированную модель роста дендритов.
- Рассмотреть алгоритм построения модели роста дендритов.
- Построить модель роста дендритов.
- Исследовать зависимость от времени числа частиц в агрегате и его среднеквадратичного радиуса в разных режимах.
{{% /callout %}}


{{% callout note %}}
# Теоретические сведения о модели
{{% /callout %}}

{{% callout note %}}

## Физические свойства вещества

- плотность $$\rho$$,
- удельная теплота плавления на единицу массы $L$, 
- теплоемкость при постоянном давлении $c_p$ (также на единицу массы),
- коэффициент теплопроводности $\kappa$ (для простоты будем считать теплопроводность и плотность не зависящими от температуры и одинаковыми для твердой и жидкой фаз – так называемая симметричная модель),
- температура плавления $T_m$.
{{% /callout %}}

{{% callout note %}}
## Переохлаждение расплава

Безразмерное переохлаждение:
$$
S = c_p \frac{(T_m - T_\infty)}{L} \tag{1}
$$

При $S \geq 1$ — полное затвердевание, при $S < 1$ — частичное.
{{% /callout %}}

