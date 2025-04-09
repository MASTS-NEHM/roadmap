---
layout: page
title: Transport modelling
permalink: /transport-modelling/
parent: Other models
nav_order: 3
---

## Transport modelling including particle tracking
Often the main requirement for a model is to predict where some substance (whether conservative or non-conservative) is transported by the flow of water. This may include heat, salinity (or freshwater), nutrients, pollutants, biological organisms etc.  The transport may be modelled by an advection-dispersion module within the main hydrodynamic code or by a post-processing step, whereby the model currents are saved and used after the main hydrodynamic model run has been completed. Where the transported substance may be represented as particles (representing individual particles or groups of ‘real’ particles, with some characteristic), this may be referred to as a ‘particle-tracking’ model and may be run within the hydrodynamic code or offline, forced by previously saved hydrodynamic output. The latter has the advantage that movement of particles can be simulated independently of the (often more computationally expensive) hydrodynamics. Outputs from this type of model may be used to derive spread distributions of the focal substance, and in the case of “biological” particles, can be used to understand larval connectivity and its role in population dynamics. 

