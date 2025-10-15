---
title: "StochasticRounding.jl: Up or down, maybe both?"
excerpt:  "Stochastic rounding introduces random numbers in every little +, -, *, /, ... with big impacts on large scales of a simulated system"
header: StochasticRounding.jl: Up or down, maybe both?
teaser: https://github.com/user-attachments/assets/177e601a-1ce0-4f2a-af18-75367fb894f3
share: false
featured_figure: 
  image: https://github.com/user-attachments/assets/177e601a-1ce0-4f2a-af18-75367fb894f3

tags:
  - Scientific computing
  - GPU programming
  - Stochastic
---

Everytime you add, subtract, multiply, ... two numbers the result, if not representable as floating-point number of a
given precision, has to be rounded. The conventional way of doing this is using deterministic round to nearest.
If only integers where representable, then sqrt(2) would always yield 1. This introduces an error that can accumulated
during an algorithm and heavily flaw an entire simulation. Given the high precision of 64-bit floating-point numbers
this problem is reduced but it never entirely goes away. So you may ask, what if we rounded sqrt(2) = 1.41... at
a chance of 41% to 2 and 59% chance down to 1. On average that would be correct and yields visibly better results:
 
<img width="60%" alt="4 4Percent" src="https://github.com/user-attachments/assets/9efb3c2e-6724-4c12-9906-b3f34ddb3f10" />

In scientific computing, stochastic rounding is new emerging rounding mode that is not (yet?) widely available on
hardware. Your CPU/GPU simply doesn't support it as people in the 1980s did not think that might be a good idea
(the IEEE standard on floating-point numbers is from 1985 and persists in having a very strong legacy on computing today).
But especially for low precision simulations where rounding errors are larger but simulations become much more efficient,
e.g. for 16-bit computing memory footprint is usually only 25% compared to 64 bits and GPU can be not just 4x but sometimes
even 16x faster (check Nvidia's TensorCores for example).

So we built Julia's [StochasticRounding.jl](https://github.com/milankl/StochasticRounding.jl) emulator (it's a registered Julia package)
that lets you play with stochastic rounding on Float64, Float32, Float16 or BFloat16 and we can do research on the impact
of this stochastic rounding on weather and climate simulations, for example:

<img width="60%" alt="4 5Turbulence6416bit" src="https://github.com/user-attachments/assets/0787deb9-6fc2-48d4-80fa-38bc2d6d9b96" />

In many cases stochastic rounding has a very beneficial impact, effectively increasing the precision at the efficiency
and memory footprint of low-precision computations (assuming your hardware supports it at no extra cost) and with
the additional benefit of stochasticity in the system. Sure, this brings up questions of reproducibility but also
in many cases stochastic approaches are used to represent uncertainty in the simulated systems, e.g.
stochastic perturbations of initial conditions or parameters in weather forecasting. See also

- Klöwer, M, PV Coveney, EA Paxton and TN Palmer, 2023. *Periodic orbits in chaotic systems simulated at low precision*, **Scientific reports**, [10.1038/s41598-023-37004-4](https://doi.org/10.1038/s41598-023-37004-4)|
- Paxton EA, M Chantry, M Klöwer, L Saffin, TN Palmer, 2022. *Climate Modelling in Low-Precision: Effects of both Deterministic & Stochastic Rounding*, **Journal of Climate**, [10.1175/JCLI-D-21-0343.1](https://doi.org/10.1175/JCLI-D-21-0343.1)|
