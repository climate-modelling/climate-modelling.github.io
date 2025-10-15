---
title: "[OPEN] Fast yet flexible: Atmospheric modelling and high-perfomance computing on the GPU"
# excerpt:  "test test test"
header:
teaser: "https://github.com/milankl/StochasticRounding.jl/blob/55a74db797d2d58c44224b9d5ceb7eec97663f73/figs/logo.png"
share: false
# featured_figure: 
#   image: "https://www.science.org/cms/10.1126/sciadv.aay4740/asset/5f0263bd-fc33-4dc6-87df-46a19f3ab895/assets/graphic/aay4740-f2.jpeg"
# learn_more: https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2021MS002954
code: http://github.com/milankl/StochasticRoudning.jl
# data: https://doi.org/10.5281/zenodo.5196512

# tags:
#   - test1
#   - test2
#   - test3
---

Atmospheric general circulation models form the backbone of Earth-system models, simulating the fastest processes in the climate system
that most heavily impact humans and nature. They represent wind, pressure, temperature, humidity, and many atmospheric processes
interlinking these variables: Radiation, clouds, surface fluxes from or to ocean and land, precipitation or convection.
The equations solved are derived from Navier-Stokes and include highly turbulent flows around mountains, planetary waves as well as
stratospheric vortices. But the equations are extended to include processes that cannot be resolved explicitly, e.g.
precipitation which happens on spatial scales much smaller than what is computationally affordable.
High-resolution weather and climate models are a massive high-performance computing endeavour.
The future of scientific computing is on graphics processing units (GPUs) which apply instructions on large arrays in parallel
and therefore require a specific programming style which is different from sequential CPU computing whereby one instruction
is executed after another. GPU computing is also the computational backbone of any sophisticated machine learning model.

This project will focus on numerical (and machine learning) modelling for the GPU using SpeedyWeather, 
a fast, atmospheric general circulation model developed in this research group in collaboration with international partners.
Written in the Julia programming language, it shines through flexibility and modularity. It runs interactively in Jupyter or Pluto notebooks
and is designed to be particularly efficient instead of always requiring a big supercomputer to run.
SpeedyWeather therefore aims to democratise climate modelling by being freely available, easy to set up and computationally feasible
also with little computational resources (single CPU or single GPU). SpeedyWeather is actively used for both climate research and in teaching,
aiming at accelerating both through its user-friendliness for student and senior climate modelers alike. In this project you will learn
invaluable software engineering skills and focus on many aspects of numerical modelling and high-performance computing.
You will also learn the magic of how climate models are being built and contribute to the next generation of these models.
In contrast to existing climate models being written for large clusters of CPUs we will need to be a bit creative and rethink how atmospheric
models are built: With GPU computing in mind, using a modern programming language, and not based on dusty old Fortran code.

The applicant is expected to have a strong background on physics, mathematics, and/or computer science, with enthusiasm for
computer science and software engineering. Prior experience with Julia is not
required, but experience with at least one other programming language like Python, Matlab, C(++), or Fortran is preferred.
