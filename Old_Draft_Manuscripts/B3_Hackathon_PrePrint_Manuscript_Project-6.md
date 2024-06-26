---
title: 'Project 6: Phenological Diversity Trends By Remote Sensing Related Datacubes'
tags:
  - Rao Q Index
  - Time-Weighted Dynamic Time Warping
  - Landscape Heterogeneity
  - Remote Sensing
  - Time Series
authors:
  - name: First Last
    orcid: 0000-0000-0000-0000
    affiliation: 1
  - name: Second Last
    orcid: 0000-0000-0000-0000
    affiliation: 2
affiliations:
 - name: Institution 1, address, city, country
   index: 1
 - name: Institution 1, address, city, country
   index: 2
date: 03 April 2024
bibliography: paper.bib
authors_short: Last et al. (2021) BioHackrXiv  template
group: B-Cubed
event: B-Cubed Hackathon 2024 - Hacking biodiversity data cubes for policy
editor_options: 
  markdown: 
    wrap: 72
---

# Introduction:

The R package "rasterdiv" was created to calculate diversity indices
with data of the class "raster layer". Here we outline an improvement we
have made to the package alongside the relevant biological context.

## The Importance of Biodiversity Indices:

Heterogeneous ecosystems have been shown experimentally and
theoretically to provide greater utility to all the agents which
comprise that ecosystem. This is through the provision of more and more
varied niches for flora and fauna to propagate. This subsequently
increases the value of ecosystem services provided to the communities
surrounding an ecosystem. Heterogeneous ecosystems are also typically
more resilient to all manner of ecosystem disturbances. Due to the
centrality of biodiversity to healthy ecosystem functioning,
quantitative measures of biodiversity are required to understand how
ecosystems are responding to ongoing environmental changes, such as
shifting land use.

Shannon's H value has been widely used as a proxy for biodiversity, but
can be inadequate when applied to the new kinds of data generated by
remote sensing platforms (e.g. images from Earth observation
satellites). One limitation is that Shannon's H value does not consider
the distance between type of instances of observed objects (be they
species or other numeric abstractions of an observation). This treats
all objects within a dataset as equally distant from one another.

Rao's Quadratic Diversity Index (Rao's Q) adds space as a trait to its
abstraction of biodiversity by accounting for the distance between
pixels within a study site. As a spatially informed alternative to
Shannon's H, Rao's Q has been demonstrated experimentally to offer
greater efficacy when representing biodiversity in aerial remote sensing
datasets [@Rocchini:2021]. However, Rao's Q remains limited by its
inability to assess trait change over time. Current implementations of
the index only assess one snapshot of the data at a time. We set out to
overcome this limitation by incorporating Time-Weighted Dynamic Time
Warping (TWDTW) to include time as a component of the distance variable
within Rao's Q.

## The Purpose of (Time-Weighted) Dynamic Time Warping & its Ecological Utility:

Dynamic Time Warping (DTW) is a mathematical approach used to compare
data series when the timing of observations differs. It has been used in
a variety of disciplines. DTW works by finding the smallest distance
between two time series.

However, by flattening the differences in timing, biologically
significant differences can also be obscured, such as when comparing
plant phenology. For instance, many tree species require a minimum
number of Growing Degree Hours (GDH) to commence their springtime
budburst [@Fu:2019]. Other ecosystem processes typically need to
coincide with phenological events, so phenology timing represents an
important differentiating factor for time series representing ecosystems
with plants.

The TWDTW approach rectifies this by including a cost to aligning pixels
with greater temporal separation. Therefore, the TWDTW function is less
likely to match the time series to others which exhibit substantially
different phenologies. This has been successfully demonstrated by
[@Maus:2016] to classify changing land use patterns in the Brazilian
Amazon, and was a more effective tool than standard DTW when applied to
heterogeneous biological environments like these.

In this manuscript we present and demonstrate our R code to implement
phenology into Rao's Q index applied to optical remotely sensed data. We
also evaluate its efficacy than Shannon and classical Rao's index using
a small portion of a grassland in Calabria, Italy.

# Methodology:

# Results:

# Discussion:

# Jupyter notebooks, GitHub repositories and data repositories

# Acknowledgements:

# References:
