---
title: "Getting Started"
linkTitle: "Getting Started"
weight: 2
description: >
  Installation and setup
---

In this section requirements and installation procedure of BioPAL are illustrated. More detalis on installation for developers can be found on BioPAL GitHub page in the [README.md](https://github.com/BioPAL/BioPAL/tree/main/README.md).

## Prerequisites

Python 3.6 is a minimum requirement. The packages required are specified in the file [requirements.txt](https://github.com/BioPAL/BioPAL/tree/main/requirements.txt).

## Installation

Installation procedure described here makes use of the open-source package management system [conda](https://docs.conda.io/projects/conda/en/latest/).

1.  Download and unzip the current [BioPAL distribution](https://github.com/BioPAL/BioPAL) to your local hard drive.

2.  In a conda command window, type the following instruction, which creates a biopal environment ( `environment.yml` is present into the BioPAL distribution ):
	
        conda env create --file environment.yml

3.  In the same conda command window, type the following instruction, which activates the created biopal environment:
	
        conda activate biopal

## BioPAL datasets

BioPAL gives easy access to several datasets that are used for examples in the documentation and testing. These datasets are hosted on an ESA page and must be downloaded for use. Contact <biopal@esa.int> to receive access to the dataset and for more information.

## Try it out!

For executing BioPAL and producing results have a look at the [Tutorials]({{< ref "docs/tutorials" >}}).