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
    equal-contrib: true
    affiliation: "1" # (Multiple affiliations must be quoted)
  - name: Juan Alday
    orcid: 0000-0003-1459-3444
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

# Optional fields if submitting to a AAS journal too, see this blog post:
# https://blog.joss.theoj.org/2018/12/a-new-collaboration-with-aas-publishing
aas-doi: 10.3847/xxxxx <- update this with the DOI from AAS once you know it.
aas-journal: Astrophysical Journal <- The name of the AAS journal.
---
# Summary

Hot Jupiters are gaseous giant exoplanets with short orbital periods (less than about 10 days).
These planets have hot extended atmospheres and are ideal targets for atmospheric characterisation.
Detailed atmospheric characterisation not only grants us insights into individual planets, but can also inform us on how planetary systems form and evolve [@chachan_breaking_2023].
Using spectroscopic observations, we can constrain the atmospheric properties (such as chemical composition, thermal structure and aerosol distribution) of hot Jupiters, in a process known as atmospheric retrievals [@irwin_nemesis_2008; madhusudhan_temperature_2009].
The main steps involved in atmospheric retrievals are as follows: starting from the data that we wish to analyse, for example emission spectra [@lee_optimal_2012] and transmission spectra [@barstow_consistent_2017], we first need to construct a parametric atmosheric model that can be used to simulate the observed data in conjunction with a spectral simulation tool.
We then explore the parameter space of the atmospheric model to find the parameters that best fit the data using a Bayesian parameter estimation scheme [e.g, @feroz_multimodal_2008].
The resulting posterior distribution of the model parameters can then inform us
about the atmospheric properties of the planet.
There are multiple open-source atmospheric retrieval softwares that have been applied to the analsysis of both solar system and exoplanetary observations, and a catalogue of these softwares can be found in @macdonald_catalog_2023.

Our nemesispy is a Python package that can be used to constrain the atmospheric properties of transiting hot Jupiters by fitting spectra generated from atmospheric models to observations.
The radiative transfer routines of nemesispy is closely based on the FORTRAN NEMESIS library described in irwin_nemesis_2008, and we have extensively benchmarked the spectral calculations of nemesispy against the FORTRAN NEMESIS library [@irwin_nemesis_2008]. We implement the correlated k-distribution method, described in ('citations'').

# Statement of need

nemesispy is a Python package for exoplanet spectral simulation and retrieval.

`Gala` is an Astropy-affiliated Python package for galactic dynamics. Python
enables wrapping low-level languages (e.g., C) for speed without losing
flexibility or ease-of-use in the user-interface. The API for `Gala` was
designed to provide a class-based and user-friendly interface to fast (C or
Cython-optimized) implementations of common operations such as gravitational
potential and force evaluation, orbit integration, dynamical transformations,
and chaos indicators for nonlinear dynamics. `Gala` also relies heavily on and
interfaces well with the implementations of physical units and astronomical
coordinate systems in the `Astropy` package [@astropy] (`astropy.units` and
`astropy.coordinates`).

`Gala` was designed to be used by both astronomical researchers and by
students in courses on gravitational dynamics or astronomy. It has already been
used in a number of scientific publications [@Pearson:2017] and has also been
used in graduate courses on Galactic dynamics to, e.g., provide interactive
visualizations of textbook material [@Binney:2008]. The combination of speed,
design, and support for Astropy functionality in `Gala` will enable exciting
scientific explorations of forthcoming data releases from the *Gaia* mission
[@gaia] by students and experts alike.

# Acknowledgements

The authors express gratitude to the developers of many open-source Python packages used by NEMESISPY, in particular numpy [@harris_array_2020], SciPy [@virtanen_scipy_2020], and Matplotlib [@hunter_matplotlib_2007]. The authors also express gratidude to the developers of the NEMESIS library [@irwin_nemesis_2008].

# References
