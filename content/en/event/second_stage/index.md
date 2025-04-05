---
title: Presentation on the topic. Group project "Dendrite growth". Stage 2. Description of the algorithm for solving the problem

event: Group project "Dendrite growth". Stage 2.
event_url: 

location: 
address:
  street: 
  city: 
  region: 
  postcode: 
  country: 

summary: Group project "Dendrite growth". Stage 2.
abstract: 'We have prepared a presentation and presentation on the second stage of the Dendrite Growth group project.'

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
url_pdf: 'https://aachemodanova.github.io/dendrites_group_research/publication/second_stage/report.pdf'
url_slides: 'https://aachemodanova.github.io/dendrites_group_research/publication/second_stage/presentation.pdf'
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


## Relevance

The appearance of dendrites plays a key role in metallurgy and foundry production, especially during the solidification of metals and alloys, since the microstructure of the resulting dendrites largely determines the mechanical, electrical and thermal properties of the resulting materials. Studying their characteristics is important not only for a theoretical understanding of crystallization processes, but also for practice, for improving production technologies of modern materials with specified properties. 
Thus, at the second stage of the group project, an algorithm for solving the problem of crystallization modeling is described. 

**Algorithm** is a systematic sequence of actions necessary to achieve a set goal. In the context of scientific research, algorithms are important not only to improve computational efficiency, but also to ensure reproducibility of results, which is a fundamental requirement of the scientific method.

## Object and subject of research
- Dendrites, 
- Crystalline dendrites

## Goals

To describe an algorithm for solving the problem of modeling dendrite growth.

## Tasks

- Consider an algorithm for constructing a model of dendrite growth.
- Describe the main stages of the algorithm

## Definition

A dendrite is a crystal that develops with a typical branching shape resembling a fractal.  In metals, they are formed during crystallization from a supercooled melt.

# Algorithm

## Step 1: Setting the parameters
- Physical properties of the substance
- Initial conditions

## Step 2: Setting up the simulation grid

- Creation of a simulation grid.
- Initialization of the seed.

## Step 3: Calculation of the temperature field

- Application of the equation of thermal conductivity
- Calculate a new temperature distribution at each time step {{<math >}}$\Delta t${{< /math >}}
- Update the temperature values at each grid point
- Repeat calculations until a steady state or a preset time is reached.

## Step 4: Modeling Dendrite growth

- The criterion of solidification
- Using Stefan's condition
- Application of the Gibbs-Thomson condition
- Updating the parameters
- Determination of fractal dimension

![Phase and temperature field during dendrite growth](3.png)

## Step 5: Analyzing the structure of dendrites
- Morphological analysis
- Correlation analysis
- Investigation of the effect of thermal noise {{< math >}}$\delta${{< /math >}}

## Step 6: Process Visualization

![Simulation of dendrite growth](8.png)


## Conclusions
The second stage of the group project on "Dendrite growth" has been completed. As a result, the process of creating an algorithm for modeling dendrite growth was described, which includes all key stages: from setting initial parameters and configuring the computational grid to modeling the growth process and detailed analysis of the obtained structures.
