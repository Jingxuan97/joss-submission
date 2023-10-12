---
title: 'nemesispy: A Python package for simulating and retrieving hot Jupiter spectra'
tags:
  - Python
  - astronomy
  - exoplanets
  - spectroscopy
  - radiative transfer
  - atmospheric retrieval

authors:
  - name: Jingxuan Yang
    orcid: 0009-0006-2395-6197
    affiliation: "1" # (Multiple affiliations must be quoted)
  - name: Juan Alday
    orcid: 0000-0003-1459-3444
    corresponding: false # (This is how to denote the corresponding author)
    affiliation: 2
  - name: Patrick Irwin
    orcid: 0000-0002-6772-384X
    corresponding: false # (This is how to denote the corresponding author)
    affiliation: 1
affiliations:
 - name: Department of Physics, University of Oxford, Parks Road, Oxford OX1 3PU, UK
   index: 1
 - name: School of Physical Sciences, The Open University, Walton Hall, Milton Keynes MK7 6AA, UK
   index: 2
date: 13 August 2017
bibliography: paper.bib
---
# Summary

Hot Jupiters are gaseous giant exoplanets with short orbital periods (less than about 10 days).
These planets have extended atmospheres with large scale heights and are ideal targets for atmospheric characterisation.
Detailed atmospheric characterisation not only grants us insights into individual planets, but can also inform us on how planetary systems form and evolve [@chachan_breaking_2023].
Using spectroscopic observations, we can constrain the atmospheric properties of hot Jupiters such as chemical composition, thermal structure and aerosol distribution, in a process known as atmospheric retrievals [@irwin_nemesis_2008; @madhusudhan_temperature_2009].
The main steps involved in atmospheric retrievals are as follows: starting from the data that we wish to analyse, for example emission spectra and transmission spectra of exoplanets [@lee_optimal_2012; @barstow_consistent_2017], we first need to construct a parametric atmosheric model and a spectral simulation tool that can be used to simulate the observed data.
We then explore the parameter space of the atmospheric model to find the parameters that best fit the data using some Bayesian parameter estimation scheme [e.g., @feroz_multimodal_2008].
The resulting posterior distribution of the model parameters can then inform us
about the atmospheric properties of the planet.
There are multiple open-source atmospheric retrieval softwares that have been applied to the analsysis of both solar system and exoplanetary observations, and a catalogue of these softwares can be found in @macdonald_catalog_2023.

# Statement of need

nemesispy is a Python package for exoplanet spectral simulation and retrieval, and is particularly useful for the retrievals of spectroscopic phase curves of hot Jupiters, which are flux measurements at multiple orbital phases and wavelengths.
The radiative transfer and spectral simulation routines are closely based on the Fortran NEMESIS library [@irwin_nemesis_2008], which has been extensively and continuously applied to the atmospheric retrievals of both solar system and exoplanetary observations [e.g., @barstow_unveiling_2020; @james_temporal_2023].
We implement the correlated k-distribution method for radiative transfer calculations, described in @lacis_description_1991.
Compared to the original NEMESIS library, the nemesispy package focuses on exoplanetary observations, with two notable points of difference.
Firstly, nemesispy implements several parametric hot Jupiter atmospheric temperature models for the retrievals of phase curve observations, including those described in @yang_testing_2023.
Secondly, nemesispy is significantly faster than the original Fortran library for modelling exoplanet spectra due to extensive code refactoring and the use of the Numba just-in-time compiler [@lam_numba_2015], which compiles the most computationally expensive routines to machine code at run time.
Such speed improvement is crucial for the analysis of exoplantary spectra using sampling-based Bayesian parameter estimation, which typically involves the computation of millions of simulated data.
In particular, nemesispy would be beneficial to phase curve retrievals [@yang_testing_2023], where each individual simulated data is relatively time consuming.

nemesispy contains a number of general purporse routines for atmospheric modelling and spectral simulations.
The modular nature of the package means that subroutines can be easily called on their own.
Currently, nemesispy has an easy-to-use API for simulating emission spectra and phase curves of hot Jupiters from arbitary input atmospheric models, and we plan to create interface for transmission spectra in our next phase of code development.
nemesispy has already been used in a scientific publication [@yang_testing_2023], and is actively being used in exoplanetary data analysis projects.
The combination of well-tested core radiative transfer routines, accelerated computational speed and packaged modular desisgn will enable exciting avenues of new research, especially with the influx of JWST data for exoplanets.

# Acknowledgements

The authors express gratitude to the developers of many open-source Python packages used by NEMESISPY, in particular numpy [@harris_array_2020], SciPy [@virtanen_scipy_2020], Numba [@lam_numba_2015] and Matplotlib [@hunter_matplotlib_2007]. The authors also express gratidude to the developers of the open-source Fortran NEMESIS library [@irwin_nemesis_2008].

# References
