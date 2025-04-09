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
