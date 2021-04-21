---
title: "Forest Disturbance"
weight: 2
description: >
  Forest disturbance algorithm description
---

Forest Disturbance (FD) is defined as an area where an intact patch of forest has been cleared, expressed as a binary classification of intact versus deforested or logged areas.

The disturbance product generation is based on Level 1 products: the restriction to severe disturbance allows the spatial resolution to be much finer than the other products since the associated changes in backscatter are expected to be several dBs in each intensity channel. The detection of changes in the polarimetric time series is based on hypothesis testing, where the null hypothesis is that in a time series of polarimetric data no change has occurred (at a given position and up to a given time). If this hypothesis fails at a given level of significance, then we assume a change has occurred. Note that it is closely related to the constant false alarm rate approach to target detection, in which the probability that an undisturbed pixel is incorrectly classified as disturbed is fixed. The estimates are updated each time a new acquisition is added to the stack, and significance levels can be attached to the test statistics.

An open issue in generating the BIOMASS disturbance product in this way is that changes in the signal caused by disturbance occur against a general background of non-forest and environmental changes. Further work is required to quantify how much these nuisance changes will increase the false detection rate. An important requirement is also to have an initial forest mask, derived from the BIOMASS data themselves or from some other source, in order to mask out detections in the non-forest areas.