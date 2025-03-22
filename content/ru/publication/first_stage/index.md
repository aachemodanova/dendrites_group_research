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

abstract: Our research group is working on a project on "Dendrite growth", in which we explore a mathematical model of this process. 


# Summary. An optional shortened abstract.
summary: Our research group is working on a project on "Dendrite growth", in which we explore a mathematical model of this process.

tags: []

# Display this page in the Featured widget?
featured: true

# Custom links (uncomment lines below)
links:
  - name: PRESENTATION
    url: https://aachemodanova.github.io/dendrites_group_research/publication/first_stage/presentation.pdf
  - name: release
    url: https://github.com/evdvorkina/study_2024-2025_mathmod/releases/tag/v9.0.0
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
    
url_pdf: 'https://aachemodanova.github.io/dendrites_group_research/publication/first_stage/report.pdf'
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
Thus, the scientific problem is to develop theoretical and numerical models capable of accurately predicting the dynamics of dendrite growth and their effect on the microstructure of formed materials. 



## Object and subject of research

- Dendrites
- Crystalline dendrites


## Goal 

To investigate the dendrite growth model.

## Tasks

- Consider a combined model of dendrite growth.
- Consider an algorithm for constructing a model of dendrite growth.
- Build a model of dendrite growth.
- To investigate the time dependence of the number of particles in the aggregate and its RMS radius in different modes.

# Theoretical description of the problem

## Definitions

A dendrite is a crystal that develops with a typical branching shape resembling a fractal.  In metals, they are formed during crystallization from a supercooled melt.

The anisotropy of a crystal is the dependence of the physical properties of a crystal on the direction of growth. That is, the crystal structure is not symmetrical, and there are several axes along which the crystal exhibits various properties (mechanical, electrical, optical).

Anisotropy is a natural consequence of the crystalline structure, since the density of atoms varies on different crystallographic planes and along different directions.

Next, we will consider the formation of a crystalline structure from a supercooled melt. 

## Basic concepts and equations

### Dendrite formation

The formation of dendrites begins with some nucleation, i.e. the first appearance of solid growth in a supercooled liquid. This formation will initially grow spherically until this shape is no longer stable. The instability of the shape has two reasons: the anisotropy of the surface energy of the solid-liquid boundary and the kinetics of attachment of particles to crystallographic planes during their formation.

It is necessary to specify the physical properties of the substance:

- density {{< math >}}$\rho${{< /math >}},
- specific heat of melting per unit mass {{< math >}}$L${{< /math >}}, 
- heat capacity at constant pressure {{< math >}}$c_p${{< /math >}} (also per unit mass),
- coefficient of thermal conductivity {{< math >}}$\kappa${{< /math >}} (for simplicity, we will consider thermal conductivity and density independent of temperature and the same for solid and liquid phases – the so-called symmetric model),
- melting point {{< math >}}$T_m${{< /math >}}.

Let the initial temperature of the melt be less than the melting point (i.e., it is supercooled) {{< math >}}$T_{\infty} < T_m${{< /math >}}. 

In the context of crystallization from a supercooled melt, dimensionless supercooling {{< math >}}$S${{< /math >}} is introduced to normalize and simplify mathematical models of the process. This parameter characterizes the degree of supercooling of the melt relative to its melting point, which is critical for initiation and crystallization rate. It is calculated using the formula (1).

{{< math >}}$$
S = c_p \frac{(T_m - T_\infty)}{L}
\tag{1}
$$ {{< /math >}}

Adiabatic conditions imply the absence of heat exchange with the environment, which means the conservation of thermal energy within the system. Under such conditions, at {{< math >}}$S\geq 1${{< /math >}}, the entire melt solidifies, since there is a sufficient temperature difference to ensure the crystallization process. At {{< math >}}$S < 1$ {{< /math>}}, only part of the melt solidifies, and we will consider this case.

We also restrict ourselves to the two-dimensional case. The thermal conductivity equation (2) is used to describe the temperature change over time in the two-dimensional case

{{< math >}}
$$
\rho c_p \frac{\partial T}{\partial t} = \kappa \nabla^2 T \equiv \kappa \left( \frac{\partial^2 T}{\partial x^2} + \frac{\partial^2 T}{\partial y^2} \right)
\tag{2}
$$
{{< /math >}}

### Dendrite growth rate

Next, we find the velocity of the crystallization boundary perpendicular to itself, and denote this velocity {{< math >}}$V${{< /math >}}. During {{< math >}}$\Delta t${{< /math >}}, a mass of matter equal to {{< math >}}$\Delta m =\rho solidifies in a section of the area {{< math >}}$s${{< /math >}} s V \Delta t${{< /math >}}.

During crystallization, the heat of melting is released {{< math >}}$\Delta Q = \Delta m L${{< /math >}}. The law of conservation of energy requires that all the heat released be removed due to thermal conductivity, the total heat flow at the boundary {{< math >}}$\mathbf{q} = -\kappa (\nabla T|_l - \nabla T|_s)${{< /math >}}

Here {{< math >}}$\nabla T|_l${{< /math >}} and {{< math >}}$\nabla T|_s${{< /math >}} are temperature gradients in liquid and solid phases, respectively. The orientation of the dendrite is determined by the external temperature gradient. Temperature gradient {{< math >}}$\nabla T${{< /math >}} is a vector whose components in the two—dimensional case are {{< math >}}$(\partial T / \partial x, \partial T / \partial y)${{< /math >}}.

The indexes {{< math >}}$l${{< /math >}} and {{< math >}}$s${{< /math >}} refer to the liquid and solid phases.

To conserve energy, the condition {{< math >}}$q s \Delta t = \Delta Q${{< /math >}} must be met. Substituting expressions for {{< math >}}$q${{< /math >}} and {{< math >}}$\Delta Q${{< /math >}}, we get (3)

{{< math >}}
$$
\kappa (\nabla T|_l - \nabla T|_s) s \Delta t = \rho s V \Delta t L
\tag{3}
$$
{{< /math >}}
By reducing the common factors {{< math >}}$s${{< /math >}}, {{< math >}}$\Delta t${{< /math >}} and considering that {{< math >}}$\mathbf{n}\cdot (\nabla T)${{< /math >}} is the projection of the temperature gradient on the normal to the boundary, you can write the scalar equation (4)

{{< math >}}
$$
\kappa (\mathbf{n} \cdot \nabla T|_l - \mathbf{n} \cdot \nabla T|_s) = \rho V L
\tag{4}
$$
{{< /math >}}

Rearranging the expression, we obtain Stefan's condition (5)

{{< math >}}
$$
\mathbf{n} \cdot \mathbf{V} = \frac{\kappa}{\rho L} (\mathbf{n} \cdot \nabla T|_s - \mathbf{n} \cdot \nabla T|_l)
\tag{5}
$$
{{< /math >}}

This equation describes the relationship between the velocity of the crystallization boundary and temperature gradients. In it, {{< math >}}$\mathbf{n}${{< /math >}} is a vector of unit length perpendicular to the boundary (the normal vector).

### Stefan's problem and the Mullins-Sekerka instability 

To determine the change in the position and shape of the solidification boundary over time, it is necessary to set the temperature at the boundary {{< math >}}$T_b${{< /math >}}. The simplest option is to accept {{< math >}}$T_b = T_m${{< /math >}}. In this case, the temperature inside the solid region will be constant, and this problem is known as the Stefan problem.

However, the solidification boundary is unstable in this case. Consider a flat boundary moving at some speed. If a small protrusion appears on it, the temperature gradient in front of the protrusion increases, which leads to an acceleration of its growth. This leads to a further increase in the gradient and acceleration of the protrusion, which characterizes the **Mullins-Sekerki instability**. This situation is similar to diffusion-limited aggregation.

In real solidification processes, such instabilities are not observed, which indicates the presence of mechanisms limiting the growth of protrusions. These mechanisms may be related to surface tension and kinetic constraints.

### The Gibbs-Thomson condition  

The first mechanism is related to surface tension. Atoms on the surface have fewer neighbors in the same phase, which leads to an increase in their potential energy. The additional potential energy is proportional to the surface area: {{< math >}}$\Delta E_p = \gamma s${{< /math >}}, where {{< math >}}$\gamma${{< /math >}} is the surface tension coefficient.

The growth of protrusions increases the surface area, which is energetically unprofitable. Therefore, the temperature of the boundary at the protrusions must be lower than the melting point in order to compensate for this energy. This is described by the **Gibbs-Thomson condition**(6):

{{< math >}}
$$
T_b = T_m \left(1 - \frac{\gamma T_m}{\rho L^2 R}\right).
\tag{6}
$$
{{< //math >}}

Here {{< math >}}$R${{< /math >}} is the radius of curvature of the boundary at a given point (for a flat surface {{< math >}}$R = \infty${{< /math >}}). The capillary radius is introduced {{< math >}}$d_0 = \gamma T_m c_p / (\rho L^2)${{< /math >}}, the size of the resulting structure is proportional to it.

### Kinetic deceleration of ledge growth  

The second mechanism is related to kinetic constraints. The attachment of atoms to a solid surface does not occur instantaneously, requiring some time during which moving sections of the boundary can supercool. This affects the temperature of the boundary (7)

{{< math >}}
$$
\Delta T_b = -T_m / \beta V.
\tag{7}
$$
{{< /math >}}

Here {{< math >}}$\beta${{< /math >}} is the kinetic coefficient.

### Dimensionless temperature and the equation of thermal conductivity

The dimensionless temperature {{< math >}}$\widetilde{T} = c_p (T - T_\infty)/L${{< /math >}} is introduced, where {{< math >}}$T_\infty${{< /math >}} is the initial temperature of the melt. The thermal conductivity equation for {{< math >}}$\widetilde{T}${{< /math >}} has the form (8)

{{< math >}}
$$
\frac{\partial \widetilde{T}}{\partial t} = \chi \nabla^2 \widetilde{T},
\tag{8}
$$
{{< /math >}}

where {{< math >}}$\chi = \kappa / \rho c_p${{< /math >}} is the thermal conductivity coefficient.

Initial condition: {{< math >}}$\widetilde{T} = 0${{< /math >}} everywhere except for the seed. When the entire substance solidifies, {{< math >}}$\widetilde{T}${{< /math >}} increases by one. Next, we omit the sign {{< math >}}$~${{< /math >}} for the variable {{< math >}}$\widetilde{T}${{< /math >}}.

# Model description

The initial position of the embryo is determined randomly. We will describe the model, for example, where we consider a square area of size {{< math >}}$N\times N${{< /math >}} nodes, with a central seed. Distance between nodes {{< math >}}$h = 1${{< /math >}}, time step {{< math >}}$\Delta t = 1${{< /math >}}.

## Temperature change

We use the equation of thermal conductivity (2). 

The exact expression for {{< math >}}$\nabla^2 T${{< /math >}} in the node {{< math >}}$(i,j)${{< /math >}} (9)

{{< math >}}
$$
\nabla^2 T \approx \frac{\langle T_{(i,j)} \rangle - T_{i,j}}{(4 + 4w)(1 + 2w) h^2},
\tag{9}
$$
{{< /math >}}

where {{< math >}}$\langle T_{(i,j)} \rangle${{< /math >}} is the average temperature value in neighboring nodes, {{< math >}}$w${{< /math >}} is a coefficient that takes into account the influence of diagonal neighbors (usually {{< math >}}$w = 1/2${{< /math >}}).

To a first approximation, a new temperature value can be written using an explicit difference scheme (10) :

{{< math >}}
$$
\hat{T}_{i,j} = T_{i,j} + \chi \Delta t \nabla^2 T.
\tag{10}
$$
{{< /math >}}

However, at the same time, only the neighbors will feel the temperature change in the node after one time step. This may be correct for high crystallization rates. Usually, however, the establishment of temperature occurs much faster than the growth of the crystal. To take this into account, one step of the crystal growth process {{< math >}}$\Delta t${{< /math >}} is divided into {{< math >}}$m${{< /math >}} steps with a duration of {{< math >}}$\frac{\Delta t}{m}${{< /math >}}. The new temperature value after step {{< math >}}$m${{< /math >}} is calculated using formula (11)

{{< math >}}
$$
\hat{T}_{i,j} = T_{i,j} + \frac{\chi \Delta t \nabla^2 T}{m}.
\tag{11}
$$
{{< /math >}}

## Dendrite growth 

The state of each node is {{< math >}}$n = 0${{< /math >}} — liquid phase, {{< math >}}$n = 1${{< /math >}} — solid phase. Intermediate states are not taken into account.

A node changes from a liquid to a solid state if it is located at the boundary and the temperature in it is lower than the local melting point. That is, condition (12) is fulfilled :

{{< math >}}
$$
T \leq \tilde{T}_m (1 + \eta_{i,j} \delta) + \lambda s_{i,j},
\tag{12}
$$
{{< /math >}}

where:

- {{< math >}}$\tilde{T}_m${{< /math >}} — dimensionless initial hypothermia,

- {{< math >}}$\eta_{i,j}${{< /math >}} is a random number in the range $[-1,1]$,

- {{< math >}}$\delta${{< /math >}} is the value of the random temperature deviation (thermal noise),

- {{< math >}}$\lambda${{< /math >}} is the value associated with the capillary radius,

- {{< math >}}$s_{i,j}${{< /math >}} is a parameter that takes into account the curvature of the boundary.

## Taking into account the curvature of the border 

The curvature of the boundary {{< math >}}$1/R${{< /math >}} is approximately calculated from the neighbors of node (13) :

{{< math >}}
$$
1/R \approx s_{i,j} = \sum_{1} n_{i,j} + w_n \sum_{2} n_{i,j} - \left( \frac{5}{2} + \frac{5}{2} w_n \right),
\tag{13}
$$
{{< /math >}}

where:

- the first amount is for the nearest neighbors,

- the second sum is based on the diagonal neighbors,

- {{< math >}}$w_n${{< /math >}} is a coefficient, usually {{< math >}}$w_n = 1/2${{< /math >}}.

Naturally, when the substance solidifies, the temperature in the node increases by 1 in our dimensionless units.

# Examples of dendrite growth patterns

Two-dimensional dendritic structures are formed under self-assembly conditions using an aqueous solution of copper sulfate and zinc plates placed in a Petri dish on filter paper. Zinc slowly displaces copper from an aqueous solution of copper sulfate, so that zinc sulfate is formed and copper precipitates in the form of dendritic structures.

- **Initial stage**: Formation of copper nuclei on the surface of the zinc plate.

- **Dendrite growth**: The organization of embryos into larger formations.

- **Structure formation**: The appearance of metallic tree-like formations with a lush crown.

- **Impurity redistribution**: During dendrite growth, copper ions diffuse from areas with high concentrations to areas with low concentrations. This redistribution of impurities affects the shape and growth rate of dendrites, creating more complex and branched structures.
This means that the impurity concentration in the liquid phase varies depending on the position and growth of the dendrites. The model uses diffusion equations to describe the redistribution of impurities (14). 

{{< math >}}
$$
\frac{\partial C}{\partial t} = D \nabla^2 C
\tag{14}
$$
{{< /math >}}

where {{< math >}}$C${{< /math >}} is the impurity concentration, {{< math >}}$D${{< /math >}} is the diffusion coefficient.

## Phase-field model

The phase-field model is one of the most common models for describing dendrite growth. It is based on thermodynamic principles and describes the kinetics of phase transitions in a system. This model uses a phase field, which is a parameter describing the state of a system (solid or liquid).

The equation of the phase field (15)

{{< math >}}
$$
\frac{\partial \phi}{\partial t} = M \nabla^2 \phi - \frac{\partial f}{\partial \phi}
\tag{16}
$$
{{< /math >}}

where {{< math >}}$\phi${{< /math>}} is the phase field, {{< math >}}$M${{< /math >}} is mobility, {{< math >}}$f${{< /math >}} — free energy.

The phase-field model allows us to take into account the influence of temperature and impurity concentration on the process of dendrite growth. It also takes into account anisotropy, that is, the dependence of material properties on the direction. This is important for accurately describing the shape and growth rate of dendrites.

 
## A model of cellular automata

The cellular automata model is used to discretely describe the growth of dendrites. In this model, space is divided into cells, each of which can be in one of several states (liquid, solid, boundary). Transitions between states are described by probabilistic rules that depend on local conditions.

- **Cell states**: Liquid, Solid, boundary.

- **Transition rules**: Probabilistic rules that depend on local conditions.

- **Influence of neighboring cells**: Interaction between cells is taken into account through local transition rules.

The cellular automata model allows us to take into account complex interactions between cells and describe the process of dendrite growth at the microscopic level. 

# Conclusions

During the first stage of the group project, we made a theoretical description of the dendrite growth model and identified the tasks of further research.

# List of references

1. Dendrite [Electronic resource]. Wikimedia Foundation, Inc., 2025. URL: https://en.wikipedia.org/wiki/Dendrite_(crystal). 
2. Fundamentals of molecular kinetic theory [Electronic resource]. Russian Technological University, 2024. URL:https://lc.rt.ru/classbook/fiz ika-10-class/osnovy-molekulyarno-kineticheskoi-teorii/6171.
3. Medvedev D. A. et al. Modeling of physical processes and phenomena on a PC: Textbook. NSU Editorial and Publishing Center, 2010. 101 p. 
4. Ermakov A.V. Structure and properties of metals and alloys. Ural Federal University, 2020. 134 p. 
5. Rakhmankulova G. A., Nasibullina D. F. Modeling of the formation of dendritic structures during metal crystallization // Young Scientist. 2017. No. 8.1. pp. 33-35.
6. Baranov V. G., Khramov A. G. Modeling of the growth process of dendritic crystal structures // Computer optics. Institute of Image Processing Systems, Iran, 2001. pp. 173-177.
