---
title: "AGB"
weight: 5
description: >
  Above Ground Biomass estimation
---


AGB stands for Above Ground Biomass and is defined as dry weight of woody matter per unit area, expressed in t/ha = Mg/ha. AGB includes the mass of live organic matter above the soil including stem, stump, branches, bark, seeds and foliage, it does not include dead mass, litter and below-ground biomass.

The relationship between P-band SAR backscatter intensity of forests and forest AGB is governed by a large number of factors related to both forest characteristics (3D structure, species, growth stage, leaf and wood water content,  etc.) and the environment (topography, soil moisture and surface roughness). AGB retrieval accounting for all these factors is ill-posed. This often led in the past to the formulation of very complex models and/or using a lot of reference data, which are usually not available on a global scale.

Level 2 Studies brought a new conceptual design of the retrieval, making full use of the BIOMASS interferometric observation capabilities to circumvent these limitations. This revision is based on three research results of the mission preparatory activities:

* the observational and modeling evidence that 30–40% of the total AGB in a dense tropical forest (BIOMASS main target area) is contained in the canopy region 25–35 m above the ground, and that the biomass in this region is highly correlated with the total AGB;
* the development of signal processing techniques (i.e., ground cancellation) to cancel out the backscatter signal from the ground layer using interferometric stacks of P-band data and Digital Terrain Model (DTM) to isolate the volume scattering element of the forest canopy;
* the development of an optimization approach to solve the model that minimizes the need for reference data.

All these results translate in the CASINO algorithm (CAnopy backscatter estimation, Subsampling, and Inhibited Nonlinear Optimisation). The algorithm inverts a power-law function relating AGB to ground cancelled backscatter data, through non-linear iterative minimization. Dimensionality of the problem is reduced by constraining the parameters according to phyisical considerations. The need for reference calibration data is minimized, though reference data still play a crucial role for absolute retrieval.