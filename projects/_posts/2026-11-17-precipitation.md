---
title: "SpeedyWeather's precipitation problem: learning to fix a biased climate model"
excerpt:  "Climate models are notoriously bad at getting rain right. Can machine learning do better than tuning the physics?"
header:
teaser: "https://github.com/user-attachments/assets/9fbd74b9-94f8-421e-b7ac-f6d76364ee7e"
share: false
featured_figure: 
  image: "https://github.com/user-attachments/assets/9fbd74b9-94f8-421e-b7ac-f6d76364ee7e"
learn_more: https://speedyweather.github.io
code: http://github.com/SpeedyWeather/SpeedyWeather.jl

tags:
  - Atmospheric modelling
  - Machine learning
  - Precipitation
  - OPEN
---

# SpeedyWeather's precipitation problem: learning to fix a biased climate model

Global climate models are notoriously bad at getting rain right: too frequent, too light, in the wrong places.
SpeedyWeather.jl, our differentiable, GPU-native atmospheric model, is no exception. Its large-scale condensation scheme
(the parameterization that converts supersaturated grid-box humidity into precipitation) has never been systematically
calibrated against observations, and likely carries the same kinds of biases seen in other GCMs. This project asks whether
machine learning can do better.

The student will run the model's baseline condensation scheme, compare it against observational precipitation datasets
(e.g. GPCP, ERA5) to characterize its biases, and then explore two ways of closing the gap: calibrating the scheme's
existing physical parameters, and training a small ML correction (or full replacement) that learns to match the observed
distribution directly. The comparison between "tuned physics" and "learned correction" is itself an interesting scientific
question: does ML buy you something beyond calibration, or does it just overfit the training years?

Depending on progress and interest, the same approach can be extended to surface humidity fluxes over ocean, land, and sea ice,
the other half of the hydrological cycle's water source. This could be either a follow-on comparison or a joint correction
alongside condensation, since biases in evaporation and condensation tend to compensate for each other in ways that make it
easy to get the right answer for the wrong reasons.

The project is a gentle, self-contained introduction to hybrid physics-ML climate modelling. There is no need to build
infrastructure from scratch: SpeedyWeather already runs efficiently on GPUs and, as a side benefit worth keeping in mind
though not the main focus, is end-to-end differentiable. This opens the door to gradient-based calibration and training
if time and interest allow. It's a good fit for someone with a precipitation background who wants hands-on experience with
both the atmospheric science of biased parameterizations and the practical mechanics of embedding ML into a physical model.
