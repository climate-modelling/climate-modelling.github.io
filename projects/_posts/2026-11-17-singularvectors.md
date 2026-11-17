---
title: "Singular-vector perturbations in SpeedyWeather.jl using automatic differentiation"
excerpt:  "Which tiny error in today's weather grows fastest into tomorrow's forecast error? Singular vectors tell you, and automatic differentiation computes them for free"
header:
teaser: "https://github.com/user-attachments/assets/9fbd74b9-94f8-421e-b7ac-f6d76364ee7e"
share: false
featured_figure: 
  image: "https://github.com/user-attachments/assets/9fbd74b9-94f8-421e-b7ac-f6d76364ee7e"
learn_more: https://speedyweather.github.io
code: http://github.com/SpeedyWeather/SpeedyWeather.jl

tags:
  - Atmospheric modelling
  - Automatic differentiation
  - Predictability
  - Scientific computing
  - OPEN
---

# Singular-vector perturbations in SpeedyWeather.jl using automatic differentiation

Singular vectors of dynamical systems identify the directions in which uncertainty in the initial conditions grows fastest.
They are used in ensemble weather forecasting to explore the distribution of possible future weather, and in particular to
better sample unlikely but possible extremes [1, 4, 5]. This project will implement initial-condition perturbations along
singular vectors in the atmospheric general circulation model SpeedyWeather, see [speedyweather.github.io](https://speedyweather.github.io) [2].
Operational weather forecasting models use a handwritten tangent linear and adjoint model to compute singular vectors.
SpeedyWeather, however, is automatically differentiable [3]: the tangent linear and adjoint models can be generated
automatically by modern compiler technology, here using the automatic differentiation framework
[Enzyme](https://enzyme.mit.edu).

## Method

For a model $dx/dt = f(x)$ denote the flow map, i.e. integrating the model forward from initial conditions $x_0$
over an optimisation time $T$, as $x(T) = \Phi_T(x_0)$. A small initial perturbation $\delta x_0$ then evolves
approximately linearly as $\delta x(T) = M \delta x_0$, where the propagator $M = \partial \Phi_T / \partial x_0$
is the Jacobian of the flow map, i.e. the tangent linear model integrated along the trajectory.
The initial perturbation that grows most over $[0, T]$, measured in a chosen norm, maximises
$\lVert M \delta x_0 \rVert / \lVert \delta x_0 \rVert$. It is the leading right singular vector of
$M = U \Sigma V^T$; the singular values $\sigma_i$ are the respective amplification factors and the left singular vectors
are the structures these perturbations evolve into at time $T$. Unlike eigenvectors of the (generally non-normal) linearised
dynamics, singular vectors capture transient, finite-time growth [6], and in the limit $T \to \infty$ the growth rates
$\log(\sigma_i)/T$ converge to the Lyapunov exponents [7].

The project proceeds in steps of increasing efficiency:

1. **Explicit Jacobian.** Compute $M$ column by column with forward-mode automatic differentiation via Enzyme
(one Jacobian-vector product, i.e. one tangent linear integration, per degree of freedom), then take a dense SVD.
This is exact for the discretised model and feasible at low resolution.
2. **Matrix-free singular vectors.** At higher resolution $M$ cannot be stored. Instead, Jacobian-vector products ($Mv$, forward mode)
and vector-Jacobian products ($M^T u$, reverse mode, i.e. the adjoint model) are passed to an iterative Lanczos
or randomised SVD algorithm to obtain only the leading few singular vectors, as done operationally [1, 4].
Reverse mode requires storing the trajectory, so checkpointing will be explored for longer optimisation times.
3. **Norms and ensembles.** Singular vectors depend on the chosen norm, e.g. kinetic or total energy [4, 8].
Ensemble members are created as the unperturbed initial conditions plus and minus scaled (and randomly combined)
leading singular vectors, following the ECMWF ensemble design [5].

## Experiments

The student will simulate ensembles of 2D turbulent flows on a rotating sphere (SpeedyWeather's barotropic vorticity model)
as a simpler alternative to the vastly more complex 3D equations used in weather forecasting.
Depending on progress the complexity can be increased to the shallow water model or to the 3D primitive equation models.
The analysis of idealised forecasts will compare the ensemble spread from singular-vector perturbations against
random perturbations, assess its sensitivity to optimisation time and norm, and test how long perturbations remain in the
linear regime. The student will develop the necessary algorithms, implement them in Julia and interact with other
SpeedyWeather developers on GitHub to guarantee correctness and performance, and write tests and documentation.

**Skills required:** Programming in either Python, Matlab, R, Fortran, C, or similar. Experience with Julia is not required, but beneficial.
Experience with data analysis and visualisation. Some background in linear algebra and dynamical systems is helpful.

## References

1. Leutbecher, M and TN Palmer, 2008. *Ensemble forecasting*, **Journal of Computational Physics**, [10.1016/j.jcp.2007.02.014](https://doi.org/10.1016/j.jcp.2007.02.014)
2. Klöwer, M et al., 2024. *SpeedyWeather.jl: Reinventing atmospheric general circulation models towards interactivity and extensibility*, **Journal of Open Source Software**, 9(98), 6323, [10.21105/joss.06323](https://doi.org/10.21105/joss.06323)
3. Moses, WS et al., 2026. **Journal of Advances in Modeling Earth Systems**, [10.1029/2025MS005615](https://doi.org/10.1029/2025MS005615)
4. Buizza, R and TN Palmer, 1995. *The singular-vector structure of the atmospheric global circulation*, **Journal of the Atmospheric Sciences**, 52, 1434-1456
5. Molteni, F, R Buizza, TN Palmer and T Petroliagis, 1996. *The ECMWF Ensemble Prediction System: Methodology and validation*, **Quarterly Journal of the Royal Meteorological Society**, 122, 73-119
6. Farrell, BF and PJ Ioannou, 1996. *Generalized stability theory. Part I: Autonomous operators*, **Journal of the Atmospheric Sciences**, 53, 2025-2040
7. Legras, B and R Vautard, 1996. *A guide to Liapunov vectors*, ECMWF Seminar on Predictability, Vol. I, 143-156
8. Palmer, TN, R Gelaro, J Barkmeijer and R Buizza, 1998. *Singular vectors, metrics, and adaptive observations*, **Journal of the Atmospheric Sciences**, 55, 633-653
