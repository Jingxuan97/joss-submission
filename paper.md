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
    orcid: 0000-0000-0000-0000
    equal-contrib: true
    affiliation: "1" # (Multiple affiliations must be quoted)
  - name: Juan Alday
    orcid: 0000-0000-0000-0000
    equal-contrib: false # (This is how you can denote equal contributions between multiple authors)
    affiliation: 2
  - name: Patrick Irwin
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

Hot Jupiters are gaseous giant planets with orbital periods less than about 10 days.
The hot extended atmospheres of these planets make them ideal targets for molecular abundance measurements using spectroscopic observations (cite:low res: transmission, emission, phase curves, high res: transmission), which can grant us valuable insights into how giant planets, and planetary systems in general, form and evolve.
The molecular abundance constraints we can glean from hot Jupiters are complimentary to the information we can gain from solar system giants, whose atmospheres are so cold that molecules such as water condense out and are hidden from view.
In order to retrieve information such as molecular abundance and thermal structure from hot Jupiter spectra, we need two modelling tools: (1) )atmospheric models to describe the planet under observation; and (2) a radiative transfer model to compute spectra that can be used to fit the data.
Our nemesispy is a Python package that can be used to constrain the atmospheric properties of transiting hot Jupiters by fitting spectra generated from atmospheric models to observations.
The radiative transfer routines of nemesispy is closely based on the FORTRAN NEMESIS library described in irwin_nemesis_2008, and we have extensively benchmarked the spectral calculations of nemesispy against the FORTRAN NEMESIS library. We implement the correlated k-distribution method, described in ('citations'').

[@irwin_nemesis_2008] [@yang_testing_2023-3]

# Statement of need

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

# Mathematics

Single dollars ($) are required for inline mathematics e.g. $f(x) = e^{\pi/x}$

Double dollars make self-standing equations:

$$
\Theta(x) = \left\{\begin{array}{l}
0\textrm{ if } x < 0\cr
1\textrm{ else}
\end{array}\right.
$$

You can also use plain \LaTeX for equations
\begin{equation}\label{eq:fourier}
\hat f(\omega) = \int_{-\infty}^{\infty} f(x) e^{i\omega x} dx
\end{equation}
and refer to \autoref{eq:fourier} from text.

# Citations

Citations to entries in paper.bib should be in
[rMarkdown](http://rmarkdown.rstudio.com/authoring_bibliographies_and_citations.html)
format.

If you want to cite a software repository URL (e.g. something on GitHub without a preferred
citation) then you can do it with the example BibTeX entry below for @fidgit.

For a quick reference, the following citation commands can be used:

- `@author:2001`  ->  "Author et al. (2001)"
- `[@author:2001]` -> "(Author et al., 2001)"
- `[@author1:2001; @author2:2001]` -> "(Author1 et al., 2001; Author2 et al., 2002)"

# Acknowledgements

The authors express gratitude to the developers of many open-source Python packages used by NEMESISPY, in particular numpy (Harris et al., 2020), SciPy (Virtanen et al., 2020), and Matplotlib (Hunter, 2007).

# References
