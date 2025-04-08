---
layout: page
title: Representing Infrastructure
parent: Ocean modelling
permalink: /infrastructure_representation/
nav_order: 6
---

# Representation of infrastructure or forcing and illustrative examples

## Climate impact on fjord and sea loch circulation 	
Estuaries are dynamic but also fragile transition areas between the salty water from the ocean and the fresh water from the rivers. With the threatening climate change, and the growing impact of human infrastructures, estuarine circulation and its water properties are likely to be affected. In particular, climate projections show that seasonality and magnitude of river discharge are expected to be altered. For fjords and sea lochs, which are usually deep estuaries possessing one or more sills, circulation have density driven dynamic coming from high freshwater input. Consequently, in estuaries with fjord-like geometry, changes in river discharge can deeply transform the stratification profile and the exchange between salty water and fresh water. In return, this can potentially drive more exposure to contaminants and pollutants, benefit to harmful algae blooms or impact aquaculture. Therefore, understanding the impact of changing environmental processes on fjords and sea lochs circulation can provide useful tools to prevent or adapt to their consequences.

This motivated the creation of Feta2D, a fast and flexible circulation model for long time-scale analysis that is developed at the University of Strathclyde. Feta2d is a model adapted to fjord and sea-loch circulation that is based on the solver technics of Eta2d (MacCready 2007), a coastal plain estuaries model. It uses an intermediate approach between the simple box model which runs fast but provide poor details, and the complex 3D models like FVCOM, which has high resolution, but is computationally expensive. The model uses a 2D cartesian grid (vertical and along-channel dimension) with Reynolds Averaged Navier-Stokes (RANS) equations, that are averaged over the tidal cycle and the channel width to improve speed efficiency. Finally, this implementation provides an efficient modelling tool that is easy to adapt to a variety of scenarios. A first application to the Puget Sound (a fjord located on the Pacific coast of USA) is on-going, and it will help discern the possible long-term changes in estuarine circulation driven by regional environmental changes. Feta2D is planned to become an open-source code in 2020, and can easily be applied to a large family of estuary with fjord-like geometry, including Scottish sea lochs.

Example of salinity profile output from Feta2d model using a transect of the Puget Sound and the Strait of Juan de Fuca 

MacCready, P. (2007). Estuarine Adjustment. J. Phy. Oceanogr., 37, 2133-2145.

## Response to projected climate

## Biological population connectivity
In many circumstances it can be useful to understand the connections between spatially separated biological populations. This information can help to identify key areas of habitat, the impact of addition or removal of habitat (Adams et al. 2014) and changes in flow regime (Millar et al. in prep.), patterns of population dynamics (Adams et al. 2015, Rabe et al., ECSS, submitted), and approaches to management of pest species (aquaculture parasites, for example; Salama et al. 2017). 

To derive estimates of connectivity, outputs from hydrodynamic models are used to drive a particle tracking model with a defined timeframe, spatial domain and configuration of habitat sites. An example, derived from salmon farm location on the west coast of Scotland, is given in ***FIGURE***. Particles with a defined set of characteristics (in this case, a time period for development of ability to settle, a mortality rate, a maximum lifespan, and a vertical position) are released from the defined habitat sites. Particles may be released in a single event, or continuously over time, in order to account for tidal effects and/or variability in meteorological conditions. Their locations are recorded over time at defined intervals, allowing the generation of density surfaces ***FIGURE connectivity A***. Any particles moving close to a habitat site after they have become able to settle are considered to make a connection between the origin/source site and the site it has passed close to. This can be summarised in a connectivity matrix ***FIGURE connectivity B ***. Connectivity matrices can be analysed in isolation in order to understand network structure (and the role of habitat sites in the overall population), or they can be applied to describe the redistribution of organisms by dispersal in population models.

Figure connectivity A: spread of infective copepodid sea lice particles from salmon aquaculture sites on the west coast of Scotland 

Figure connectivity B: Connectivity between salmon aquaculture sites on the west coast of Scotland.

## Sharing of resources between tidal developments
