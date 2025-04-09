---
layout: page
title: Hydrodynamic models
parent: Ocean modelling
permalink: /hydrodynamic-models/
nav_order: 1
---

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

## Model diagnostics 
The model output can be analysed over time and used for forecast guidance and other applications; such as operational modelling for water level and current forecast guidance, ecological and geospatial applications. This can be either in the form of local diagnostics (eg. virtual ADCP) through to writing out the entire simulation state (eg. velocity, pressure, etc.) for the entire domain. For example, analysing water level time series to calculate the average of the high and low water values can be used to determine the tidal datums. These results can be useful to a wide range of maritime community, providing that sufficient accuracy has been demonstrated from the model. The accuracy of the model can be determined by comparing the model output against real measurements of the water-levels and current velocities.
