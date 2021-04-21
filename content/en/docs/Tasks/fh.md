---
title: "Forest Height"
weight: 4
description: >
  Forest Height estimation
---


Forest Height (FH) is defined as upper canopy height according to the H100 standard used in forestry expressed in meters. H100 is defined as the average height of the 100 tallest trees/hectares.

The baseline methodology for BIOMASS interferometric phase is implemented by means of PolInSAR. Polarimetric-interferometric correlations estimated from data are linked to forest structural parameters such as forest height, ground-to-volume ratio, canopy extinction and temporal decorrelation through the Random Volume over Ground (RVoG) model. This model assumes that forest scattering comes from an extended layer of height equal to the canopy height above an opaque ground layer. The vertical distribution of scatterers is weighted by an extinction function, accounting for electromagnetic attenuation through the vegetation. The propagation through the volume is assumed to be independent of polarization.

The main challenges for BIOMASS are the presence of ground scattering in all polarizations due to the limited extinction at P-band, the limited resolution available at 6 MHz and temporal decorrelation due to the three-day repeat cycle. During the tomographic phase, FH will be estimated from the upper envelope of the tomographic voxel intensity, as well as the Digital Terrain Model (DTM) from the lower envelope to be ingested to the RVoG model as a-priori.