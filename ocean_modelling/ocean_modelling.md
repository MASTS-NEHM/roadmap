---
layout: page
title: Ocean modelling
permalink: /ocean-modelling/
nav_order: 4
---

# Introduction to ocean modelling

## What are models? conceptual, numerical and physical
Scientific analysis of any real world problem requires some abstraction and conceptualization to a representation that can be readily analysed. These representations or models can take a wide range of forms that are amenable to analysis. 

Models may be physical, statistical or mathematical. Physical models (or experimental models) usually involve a downscaled physical representation of (what are conceptualised as) the essential characteristics of the subject of the study. Examples would include a faithful scale- model of a particular harbour or coast region and flumes and wave tunnels with a simple or idealized geometry. Physical models are often used for studies of coastal processes and coastal engineering projects. They are rarely used for studies of regional coastal waters.

Mathematical models require and follow from the representation of the subject by equations. Mathematical models can be analytical or numerical. A simple abstraction of a real world problem may be sufficiently simple to allow an analytical (and sometimes exact) solution of the equations and may be very useful. However, if the representation is too simplistic for the objective, then a more complicated representation may be necessary, such that an analytical solution is impossible. In this case, numerical methods are necessary, usually solving the partial differential equations. Most numerical models require some form of “time stepping” in which an estimation of the progress of the state of the subject to a later time is calculated from the original state and the governing equations, although steady-state models e.g. assuming a periodic solution, may also be used. Many coastal ocean models (“3D models”) also discretize a volume of water into increments of depth, latitude and longitude and within a timestep, movement of properties between adjacent spatial increments are also calculated. Resolving a domain (the period and volume of interest) into a very large number of discrete elements is the origin of the high demand of most numerical models on computing resources (both the number of computations and the data storage). Simpler models can be useful and reduce the computing demand. Depth-averaged (“2D”) models are common and are sufficient for some applications. Simpler but useful representations for some purposes include “box models” that consider a small number of discrete elements and circuit analogues. Numerical models are widely used to describe coastal regions and can also be used to study particular processes. Numerical models are the default tool for most coastal ocean modelling and will be the main subject of this document.

Statistical models rely on data and are especially useful where mechanistic understanding is insufficient for a plausible numerical model to be constructed. Statistical modelling can also be used in the analysis of the output from numerical models, especially where the outputs are too large or complicated for direct interpretation. Statistical modelling will certainly remain a large part of the analysis of most numerical coastal ocean models, but otherwise are beyond the scope of this document.

## What is a coastal hydrodynamic model?

### Overview
Hydrodynamic models are used to simulate water motion in coastal regions, and can model a range of processes from the sub-metre (engineering) scale, up to hundreds of kilometres (regional scale). They can be applied to both marine biological (environmental) and engineering concerns, or indeed simultaneously both: applications can be in pollution transport, algal blooms, sea lice propagation from (and to) fish farms, tidal resource estimation and environmental impact assessments for tidal farms.

Historically, hydrodynamic models were physical models built to scale, but with advances in computational power, using hydrodynamic numerical models became more common and widely used. Hydrodynamic numerical models are mathematical models that usually solve, in some form, the Navier-Stokes momentum equations (themselves derived from Newton’s equations of motion, under certain assumptions), and can predict the future state of fluid systems for a given initial state. At the very least, the state consists of the surface elevation, velocity, pressure, but frequently also includes salinity, density, temperature, turbulence parameters and tracer terms. Typically, they start from ‘at rest’, meaning the water within the model domain is initially static, and then tidal (or other) forcing at the boundaries is used to drive the flow through the domain. Optionally, these boundary conditions can also include velocity terms and turbulence parameters. Surface atmospheric forcing can also be used to drive the model.
The many features and facets of hydrodynamic models

### Discretisation schemes
There are three fundamental types of discretisation schemes historically popular in hydrodynamic models, each of which have various strengths and weaknesses. These are: i) finite difference, ii) finite element and iii) finite volume methods. Interleaved with the use of these are structured and unstructured grids. As their names imply, structured grids have a regular structure, meaning that the grid cells, the fundamental spatial unit of the model, cannot have an arbitrary geometry or arrangement: rather both are very tightly specified. This can be a problem in coastal modelling, which gets around such issues by labelling cells either wet (ie. containing water) or dry (on land). Whilst this may seem like a major disadvantage, the considerable advantage of structure grids is that in the right circumstances, their use can be orders of magnitude more computationally and memory efficient [REF needed]. 

Identify difference between hydrodynamic and CFD (computational fluid dynamics) models - probably now these overlap considerably).

Finite volume methods (FVM) [1][2] were developed to tackle highly turbulent flow with Reynolds numbers orders of magnitude higher than were possible with finite difference methods of the time. FVM does this by using an integral rather than differential form of the Navier Stokes momentum equations, which ensures that the momentum is conserved on a local per-cell basis, rather than a global (domain) scale as with finite difference schemes. Synonymous with this was the development of the SIMPLE scheme by Patankar and Spalding [1978 ref] which dealt with the problem of coupling pressure and momentum terms that both must be solved simultaneously. Finite volume schemes are prevalent in engineering due to their stability when modelling turbulent flows, but also are used in the very popular FVCOM regional coastal model. The main disadvantage of FVM is that it is low order; this means that high order (ie. polynomial) representations of velocity are not possible beyond quadratic interpolation without great computational expense. This means that unless a specialised wall model is used, boundary layer flows cannot be adequately resolved and thus estimations of bed stress will be inaccurate. FVM can however be naturally adapted to unstructured grids, which makes them suitable for dealing with irregular domains. With unstructured grids, the geometry and order of cells within a grid can be entirely arbitrary, thus will readily fit to coastal domains.

Finite element methods (FEM) [REFS] originally evolved for structural analysis in civil and mechanical engineering, but have since been adapted to computational fluid dynamics problems. Finite elements use what are called basis functions to describe fluid prognostics such as pressure and velocity. These basis functions can be of arbitrary order, and so very high order elements can be used to say, resolve velocity shear in a boundary layer. However, in their original formulation, where these basis functions were continuous across elements, high Reynolds number flows such a coastal problems were not practical due to the instability of the continuous discretisation. In recent developments, discontinuous basis functions have been developed, which, by breaking the continuity of velocity field can impose local momentum continuity. This has made discontinuous FEM suitable for highly turbulent flow; moreover these can be on unstructured grids as FEM naturally adapts to such grids. However, they are currently quite computational expensive to run, as the discontinuity increases the degrees of freedom of any given problem by almost an order of magnitude. 

### References

1. S. Patankar. Numerical Heat Transfer and Fluid Flow. CRC Press, 1980.
2. H. Versteeg. An Introduction to Computational Fluid Dynamics: The Finite Volume Method. Prentice Hall, 2007.

<!--
* Finite-difference, finite-element, finite-volume
* Depth-integrated
* Sigma layer models - discuss the vertical coordinate system - this can be z-levels, sigma-levels (usually used in coastal and shelf seas), or hybrid coordinate.
* Hydrostatic, non-hydrostatic
* Turbulence models (RANS, eg. k-epsilon, k-omega SST, Large Eddy Simulation, Mellor-Yamada, GOTM)
-->

### Model diagnostics 
The model output can be analysed over time and used for forecast guidance and other applications; such as operational modelling for water level and current forecast guidance, ecological and geospatial applications. This can be either in the form of local diagnostics (eg. virtual ADCP) through to writing out the entire simulation state (eg. velocity, pressure, etc.) for the entire domain. For example, analysing water level time series to calculate the average of the high and low water values can be used to determine the tidal datums. These results can be useful to a wide range of maritime community, providing that sufficient accuracy has been demonstrated from the model. The accuracy of the model can be determined by comparing the model output against real measurements of the water-levels and current velocities.

## Other models

In general, model systems are now being developed, in which the core is a 3D baroclinic, hydrodynamic model, but there are also ancillary models, which may be more or less closely coupled with the hydrodynamic model. There are many interaction processes in which contributions from other dynamic models may be affected (either 1-way or 2-way) by processes in other models. Examples include the atmospheric forcing terms for heat or momentum, in which parametrisations of fluxes may include effects of the surface of the ocean, such as SST or waves in the formulation.
