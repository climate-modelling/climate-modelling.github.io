---
title: "An unbiased atmospheric climate model"
excerpt:  "To correct the large biases in state-of-the-art climate models with a ML model of the sub-grid tendencies."
header: "An unbiased atmospheric climate model"
teaser: https://github.com/user-attachments/assets/9c8dd01c-405e-4f5c-8e8b-f2603642a507
share: true
featured_figure: 
  image: https://github.com/user-attachments/assets/9c8dd01c-405e-4f5c-8e8b-f2603642a507
learn_more: https://www.sciencedirect.com/science/article/pii/S1463500316301688
code:
data:

tags:
  - Scientific computing
  - Atmospheric modelling
  - Stochastic
  - OPEN
---

# An unbiased atmospheric climate model

Miniproject for CDT/DTP rotations, with [Fenwick Cooper](https://www.physics.ox.ac.uk/our-people/cooperf)
and [Charlotte Merchant](https://intelligent-earth.ox.ac.uk/people/charlotte-merchant)

https://github.com/user-attachments/assets/b2b87f47-c357-4a11-8799-802905ef4a12

### Goal

To correct the large biases in state-of-the-art climate models with a ML model of the sub-grid tendencies.
The novel aspect of the project is to produce a climate model that has a much more accurate:

1.	Climatological mean state.
2.	Climatological variability.
3.	Dynamical response to a forcing.

The method we will use has a solid theoretical basis. It has been demonstrated to work in practice in ocean models,
and it is similar in philosophy to the sub-grid modelling used in Neural GCM. However, it has never been applied to the atmosphere,
where convection might be a dominant complicating factor.

### Theoretical justification

We can’t explicitly resolve everything in an atmosphere model. The sub-grid needs to be represented somehow.
Simplified models of the sub grid processes are called parametrisations. We cannot derive the parameterisations
entirely from theory because despite over 100 years of effort, we don’t have a theory of turbulence.
Currently, educated guesses of the sub grid processes are used, supplemented by measurements.
However, their impact still leads to large biases. To ensure removal of these biases, many empirical constants are required.
The theory for how to optimise the values of these constants has been developed and needs to be tested for the first time.

### Method

A proof-of-concept experiment will provide a target climatological state using Speedy Weather at high resolution in a Held and Suarez configuration.
A simple stochastic parameterisation of the sub-grid flow will be implemented in a low-resolution equivalent.
The parameters of this stochastic model will be optimised to force the low-resolution model towards the high-resolution climatology.
We will test how well the low-resolution model responds to climate forcing. If successful, the procedure can be extended to model
sub-grid convection and then applied to a state-of-the-art climate model.

### Reference

- Cooper F. C., 2017, *Optimisation of an idealised primitive equation ocean model using stochastic parameterization*, **Ocean Modelling**, [10.1016/j.ocemod.2016.12.010](https://www.sciencedirect.com/science/article/pii/S1463500316301688)
