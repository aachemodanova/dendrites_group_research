---
title: 'Group project "Dendrite growth". Stage 2: Description of the algorithm for solving the problem'

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

abstract: Our research group is working on a project on "Dendrite growth", in which we explore a mathematical model of this process and the algorithm for solving the problem.


# Summary. An optional shortened abstract.
summary: Our research group is working on a project on "Dendrite growth", in which we explore a mathematical model of this process and the algorithm for solving the problem.

tags: []

# Display this page in the Featured widget?
featured: true

# Custom links (uncomment lines below)
links:
  - name: PRESENTATION
    url: https://aachemodanova.github.io/dendrites_group_research/publication/second_stage/presentation.pdf
  - name: release
    url: https://github.com/evdvorkina/study_2024-2025_mathmod/releases/tag/v10.0.0
  - name: report_md
    url: https://github.com/evdvorkina/study_2024-2025_mathmod/blob/master/project-group/stage2/report/report.md
  - name: report_pdf
    url: https://github.com/evdvorkina/study_2024-2025_mathmod/blob/master/project-group/stage2/report/report.pdf
  - name: report_docx
    url: https://github.com/evdvorkina/study_2024-2025_mathmod/blob/master/project-group/stage2/report/report.docx
  - name: presentation_md
    url: https://github.com/evdvorkina/study_2024-2025_mathmod/blob/master/project-group/stage2/presentation/presentation.md
  - name: presentation_pdf
    url: https://github.com/evdvorkina/study_2024-2025_mathmod/blob/master/project-group/stage2/presentation/presentation.pdf
  - name: presentation_html
    url: https://github.com/evdvorkina/study_2024-2025_mathmod/blob/master/project-group/stage2/presentation/presentation.html
    
url_pdf: 'https://aachemodanova.github.io/dendrites_group_research/publication/second_stage/report.pdf'
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

<iframe width="720" height="405" src="https://rutube.ru/play/embed/4044988bf092e351e477b7352888bef9/" frameBorder="0" allow="clipboard-write; autoplay" webkitAllowFullScreen mozallowfullscreen allowFullScreen></iframe>

<iframe width="560" height="315" src="https://plvideo.ru/embed/vIeydVQu--Je" title="Platform video player" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

# Introduction

## Relevance

The appearance of dendrites plays a key role in metallurgy and in foundry production, especially during the solidification of metals and alloys, since the microstructure of the resulting dendrites largely determines the mechanical, electrical and thermal properties of the obtained materials. Studying their characteristics is important not only for a theoretical understanding of crystallization processes, but also for practice, for improving production technologies of modern materials with specified properties. 

Thus, at the second stage of the group project, an algorithm for solving the crystallization modeling problem is described. 

**Algorithm** is a systematic sequence of actions necessary to achieve a set goal. In the context of scientific research, algorithms are important not only to improve computational efficiency, but also to ensure reproducibility of results, which is a fundamental requirement of the scientific method.

## Object and subject of research

- Dendrites
- Crystalline dendrites

## Goals

To describe an algorithm for solving the problem of modeling dendrite growth.

## Tasks

- Consider an algorithm for constructing a model of dendrite growth.
- Describe the main stages of the algorithm

# Algorithm

## Step 1: Setting the parameters

At the first stage, the initial state of the system is set, which includes all the necessary physical parameters of the material and boundary conditions for simulation. Special attention is paid to the correctness of the initial data assignment, since the reliability of the entire modeling process depends on it.
### Physical properties of the substance:

- Density {{<math>}}$\rho${{</math>}}: Determines the mass of a unit volume of a material and affects the thermal balance of the system. The higher the density, the more energy is required for heating.
- Specific heat of melting {{<math >}}$L${{< /math>}}: Characterizes the energy required for the transition of a substance from a solid phase to a liquid without changing the temperature.
- Heat capacity {{<math >}}$cp${{</math>}}: Shows the amount of energy required to heat a unit of mass by one degree. It is important for calculating the dynamics of temperature changes.
- Coefficient of thermal conductivity {{<math >}}$\kappa${{< /math >}}: reflects the ability of a material to transfer thermal energy. Determines the rate of equalization of temperature gradients.
- Melting point {{<math >}}$T_m${{< /math>}}: The critical point at which the phase transition begins.
- Surface tension coefficient {{<math >}}$\gamma${{< /math>}}: affects the shape of the interface.
- `Anisotropy` parameters: determine the direction of preferential growth [1].

![Physical properties of a substance using Hafnium as an example](2.png)
    
### Initial conditions:

- Initial melt temperature {{<math >}}$T_∞${{< /math >}}: Sets the degree of supercooling of the system. Determines the potential for the start of crystallization.
- Dimensionless hypothermia {{< math >}}$S=Lcp(T_m−T_∞)​${{< /math >}}: A key parameter indicating the thermodynamic readiness of the system to start the process.
- Boundary conditions: define the behavior of the system at the boundaries of the computational domain.
- Conditions of heat exchange with the environment [2]

## Step 2: Setting up the simulation grid

In the second step, a computational grid is created to simulate the growth of dendrites. The stage consists of preparing the mesh and the initial configuration of the crystallization seed.

### Creating a simulation grid:

- Grid size {{<math >}}$N \times N${{< /math >}}:
    Defines the detail of the simulation — the number of nodes on each side. More nodes give accuracy, but require more resources.
- Spatial step {{< math >}}$h${{< /math >}}:
    The distance between adjacent grid nodes. A smaller step increases accuracy, but increases computational costs.
## Initializing the seed:

- The central region of the solid phase:
  The initial solid zone is in the center of the grid, where dendrite growth begins. Its location affects the symmetry of the process.
- Shape and size parameters:
The shape (for example, round or elliptical) and the size of the seed set the initial conditions for growth and can affect the direction and speed of crystallization [3].
  
![A function of two variables F defined on a structured grid](1.png)

## Step 3: Calculation of the temperature field

The third step is to simulate the temperature distribution in the system over time. It is the basis for the analysis of dendrite growth.

### Application of the heat equation:

- The equation of thermal conductivity (1)

{{< math >}}
$$
\rho c_p \frac{\partial T}{\partial t} = \kappa \nabla^2 T
\tag{1}
$$
{{< /math >}}

It is used to simulate temperature changes, takes into account the influx of heat into the system, as well as its distribution.

### Numerical implementation of the equation:

- Finite difference method: approximates derivatives in terms of discrete values;
- The choice of the time step {{<math >}}$\Delta t${{</math>}} and the spatial step {{< math>}}$h${{</math>}} is important for the stability and accuracy of calculations.

### Calculation steps:

- Calculate a new temperature distribution at each time step {{<math >}}$\Delta t${{< /math >}};
- Update the temperature values at each grid point;
- Repeat calculations until a steady state or a preset time is reached.

## Step 4: Modeling Dendrite growth

At the fourth stage, modeling of dendrite growth is implemented based on calculated temperature fields and corresponding physical laws.

### The criterion of solidification:

Determine the melting point {{<math>}}$T_m${{</math>}} when the temperature at a point drops below {{<math>}}$T_m${{</math>}}, it begins to solidify.

### Using Stefan's condition:

- Stefan's condition (2):

{{< math >}}
$$
V = \frac{\kappa}{\rho L} (\nabla T|_s - \nabla T|_l)
\tag{2}
$$
{{< /math >}}

It determines the growth rate of the crystallization boundary {{<math>}}$V${{< /math>}}, which makes it possible to relate the growth rate and the difference in temperature gradients at the phase boundary.
- Taking into account the velocity {{<math >}}$V${{</math>}}, the positions of the crystallization boundary are updated, simulating the expansion of the solid phase.

### Application of the Gibbs-Thomson condition:

- The Gibbs-Thomson condition (3): 

{{< math >}}
$$
T_b = T_m \left(1 - \frac{\gamma T_m}{\rho L^2 R}\right)
\tag{3}
$$
{{< /math >}}

adjusts the melting point at the crystal boundary. This takes into account the influence of surface tension and the curvature of the boundary.

### Updating parameters:

After each stage of dendrite growth, the temperature field is recalculated taking into account the heat absorbed or released due to the phase transition. 

### Definition of fractal dimension

The fractal dimension {{< math >}}$D${{< /math >}} describes the degree to which the structure fills the space.

The correlation function or scaling method (4) can be used for the calculation:

{{< math >}}
$$
N(r) \sim r^D
\tag{4}
$$
{{< /math >}}

where {{< math >}}$N(r)${{< /math >}} — the number of points inside a circle of radius {{< math >}}$r${{< /math >}}.

Necessary:

   - Select a set of points belonging to the formed structure
   - For different values of {{< math >}}$r${{< /math >}} count the number of points inside a circle of radius.
   - Plot {{< math >}}$\log(N(r))${{< /math >}} from {{< math >}}$\log(r)${{< /math >}} and find the slope of a straight line — this will be the fractal dimension {{< math >}}$D${{< /math >}} [4].

![Phase and temperature field during dendrite growth](3.png)

## Step 5: Analyzing the structure of dendrites

At this stage, the formed dendritic structures are analyzed. Their properties are evaluated and compared with theoretical and experimental data.

### Morphological analysis:

- Involves analyzing the shape and size of the dendrite, allowing you to determine the mechanisms of their growth, as well as the processes that affect it.
- The fractal dimension measurement method provides a quantitative assessment of the complexity of the dendrite structure.
 Spectral analysis examines the spatial frequencies of a structure, revealing the repeating patterns and scale of dendrite features. This helps to evaluate the regularity of branching and the overall organization of the form.

### Correlation analysis:

Evaluates the relationship between parameters (e.g. temperature and growth rate) to quantify how modeling conditions affect dendrite morphology.

### Investigation of the effects of thermal noise {{< math >}}$\delta${{< /math >}}

First, add thermal noise:

- Add a random disturbance to the temperature at each step {{< math >}}$\eta_{i,j} \delta${{< /math >}}, где {{< math >}}$\eta_{i,j}${{< /math >}} — a random variable from a segment {{< math >}}$[-1,1]${{< /math >}}.

Since thermal noise can affect the propagation velocity of the solidification front and the shape of the dendrites, the simulation should be repeated for different values {{< math >}}$\delta${{< /math >}} and compare the results, namely to evaluate how thermal noise affects:
 
- The shape of the dendrites.
- The rate of solidification.
- The fractal dimension of the formed structures.

## Step 6: Process Visualization

The sixth stage of the algorithm is the visualization of dendrite growth.

### Visualization of dendrite growth:

1. The use of graphical tools for image generation and animation illustrating the stages of dendrite formation and their final configuration [5].

![Simulation of dendrite growth](8.png)

2. The visual representation of the data plays a key role in interpreting the results and provides an understanding of the modeled process [6].

![Dendrite Growth](5.png)

![Dendrite Growth](6.png)

![Dendrite Growth](7.png)

# Output

In the second stage of the group project, the process of creating an algorithm for modeling dendrite growth was described, which includes all key stages: from setting initial parameters and configuring the computational grid to modeling the growth process and detailed analysis of the obtained structures. 

The use of algorithms allows solving problems more efficiently and accurately, each stage makes an important contribution to the formation of a holistic understanding of the phenomenon under study.

# List of references

1. The beekeeper, Vorobyova. The Titan. Zirconium, hafnium. [electronic resource]. URL: https://en.ppt-online.org/47544.
2. D.A. Medvedev and others. Modeling of physical processes and phenomena on a PC: Textbook. Novosibirsk: Novosibirsk State University, 2010. 101 p. 
3. Calculation grid [Electronic resource]. Wikimedia Foundation, Inc., 2025. URL: https://ru.wikipedia.org/wiki/%D0%A0%D0%B0%D1%81%D1%87%D1%91%D1%82%D0%BD%D0%B0%D1%8F_%D1%81%D0%B5%D1%82%D0%BA%D0%B0.
4. Hsu Y.-R. et al. Numerical simulation of nanopost-guided self-organizationdendritic architectures using phase-field model [Electronic resource]. Wikimedia Foundation, Inc., 2018. URL: https://journals.plos.org/ploson e/article?id=10.1371/journal.pone.0199620.
5. Gif. Artificial Dendrites Growth [Electronic resource]. Wikimedia Foundation, Inc., 2025. URL: https://upload.wikimedia.org/wikipedia/commons/3/30/Artificial_dendrites_growth.gif.
6. Wang K. and others . Dendrite growth in the recharging process of zinc–air batteries [Electronic resource]. Journal of Materials Chemistry A, 2025. URL: https: //pubs.rsc.org/en/content/articlelanding/2015/ta/c5ta06366c/unauth.
