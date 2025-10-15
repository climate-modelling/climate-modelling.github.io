---
title: "Machine learning in atmospheric models with generalization in space and time"
excerpt:  "Learning the physics not a hardcoded representation of continents with their specific climates"
header:
teaser: "https://github.com/user-attachments/assets/8093e7a6-0f63-4062-bf5c-c42b689a670f"
share: false
featured_figure: 
  image: "https://github.com/user-attachments/assets/8093e7a6-0f63-4062-bf5c-c42b689a670f"

tags:
  - Machine learning
  - Numerical weather prediction
  - Generalization
---

# Machine learning in atmospheric models with generalization in space and time

If you were to take Graphcast and push the world outside of its climate distribution (think global warming) the models likely produce garbage
because in their latent space they have a hardcoded representation of, say, surface temperatures in the tropics being warmer than in mid-latitudes.
Meaning any experiment to investigate causes and consequences of global warming wouldn’t work with these models as ML architecture
would try to sample from the distribution it has seen during training. NeuralGCM addresses this problem by using a single-column ML correction that
therefore can learn, say, from the winter climate of Spain and apply it to the summer climate of the UK — because it does not actually know where
things are on the planet. Theoretically this allows for a generalisation of ML across space, diffusion/consistency models would struggle with that,
but no one has ever actually shown this, e.g. take NeuralGCM and Graphcast, flip the hemispheres, or rotate them, and see whether they
produce garbage or not. More generally this points to a shortcoming of the image-inspired ML approaches: Whereas we would like to use ML in a way that
in a climate model it adds some general truth, that generalisation is very questionable if it just has learned that region A has to be
warmer/rainer/stormier than region B.

NeuralGCM is a hybrid physics-ML atmospheric model that relies on sea surface temperatures as boundary conditions. Meaning that ramping up those
to represent global warming it will also warm the atmosphere. Great, but you technically include “forbidden” knowledge because with global warming
we actually do not know how the oceans will warm exactly. For that reason SpeedyWeather comes with simple representations of the physical processes
(clouds, precipitation, surface fluxes, …) that do give you a “knob” to actually simulate global warming by increasing CO2 in the radiation scheme —
NeuralGCM has learned all physics, so you can technically infer again that is has learned daytime heating, but there’s no way to disentangle the
different processes as they are all handled by the same neural network. This whole approach would be so that a model can be corrected with
machine learning without losing the physical model’s ability to generalise in time, meaning that you get a realistic future climate if you ramp up CO2.

