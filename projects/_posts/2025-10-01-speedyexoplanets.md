---
title: "Differentiable atmospheric modelling for Earth and exoplanets"
excerpt:  "Atmospheric general circulation models are the backbone of climate models, being used to understand and predict climate change on Earth and understand climate on exoplanets."
header:
teaser: "https://github.com/user-attachments/assets/a8bdf88a-d779-43b0-8cf2-79fee5d1d806"
share: false
featured_figure: 
  image: "https://github.com/user-attachments/assets/a8bdf88a-d779-43b0-8cf2-79fee5d1d806"
code: http://github.com/SpeedyWeather/SpeedyWeather.jl

tags:
  - Automatic differentiation
  - Exoplanets
  - Atmospheric modelling
  - OPEN
---

# Differentiable atmospheric modelling: Learning from data between Earth’s and exoplanetary climates

_supervised together with [Tad Komacek](https://www.physics.ox.ac.uk/our-people/komacek) (Oxford)_

Atmospheric general circulation models are the backbone of climate models, being used to understand and predict climate change on Earth.
Founded in physical laws, general circulation models can be generalised to exoplanetary atmospheres. While many atmospheric processes on
Earth are well understood and accurately simulated as evident through the success of weather forecasting, some processes such as cloud
formation and precipitation are less certain. Societally-relevant surface climate and extreme events like heat waves, however, strongly
depend on those. At the same time, observations can constrain such uncertainties, improving climate predictions on Earth. On exoplanets
this will reveal insights about the parameter regimes in which planetary habitability is possible. How to make atmospheric models
automatically learn from observational data? 

This project will build on top of SpeedyWeather, an atmospheric general circulation model written in the Julia programming language.
SpeedyWeather is easy to use and extend, inspired by modern software engineering, covering functionality from data visualisation to
high-performance computing. The candidate will continue to develop its differentiability through the automatic differentiation
framework Enzyme. Differentiating through SpeedyWeather, we can optimise the unknown or less certain parameters determining the
planetary surface climate and resulting habitability in the same way as neural networks are trained towards observations.
And we can add neural networks to SpeedyWeather forming a hybrid physics and data-driven model. 

For exoplanets, observations of gas giants down to hot terrestrial planets are currently used to constrain their atmospheric composition
and thermal structure. Critically, upcoming space missions such as the Large Interferometer for Exoplanets and Habitable Worlds Observatory
will have the ability to measure the thermal emission and reflected light of Earth-like exoplanets, enabling a direct test of our Earth-based
understanding of planetary climate. This SpeedyWeather/Enzyme framework will enable novel rapid inverse characterization of exoplanetary
atmospheres with a 3D model that can be applied to exoplanet observations.

Part 2 of this project will scale up the same method to the Earth’s atmosphere, increasing data and complexity. For earth, the current surface
climate is observable, but a model may still mispredict frequencies and intensities of extreme events like heat waves under global warming.
But with automatic differentiation we can train the model to correct for the missing physics of heat waves towards a more reliable generalisation
into future climates, assessing the Earth’s habitability under global warming.

This PhD project will bridge several fields: The applicant is expected to have a strong background on the spectrum between physics,
mathematics, and computer science, with enthusiasm for computer science and machine learning. Prior experience with Julia is not
required, but experience with another programming language like Python, Matlab, C(++), or Fortran is preferred.

Home fee funding (UK passport in most cases) is available overseas fee students will need to apply for internal funding
(happens automatically when directly applying to the department) or external funding.

Posted here [https://www.physics.ox.ac.uk/study/postgraduates/dphil-atmospheric-oceanic-and-planetary-physics/climate-physics](https://www.physics.ox.ac.uk/study/postgraduates/dphil-atmospheric-oceanic-and-planetary-physics/climate-physics)
