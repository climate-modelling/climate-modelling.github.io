---
title: "Data compression and bitinformation"
excerpt:  "Compressing atmospheric data into its real bitwise information content"
header: "Compressing atmospheric data into its real bitwise information content"
teaser: https://github.com/user-attachments/assets/65bb61b7-ce6f-48d7-b08d-d9fdc08c56fa
share: false
featured_figure: 
  image: https://github.com/user-attachments/assets/65bb61b7-ce6f-48d7-b08d-d9fdc08c56fa
learn_more: https://www.nature.com/articles/s43588-021-00156-2

tags:
  - Data compression
  - Information theory
  - Scientific computing
---
Hundreds of petabytes are produced annually at weather and climate forecast centers worldwide.
Compression is essential to reduce storage and to facilitate data sharing. Current techniques
do not distinguish the real from the false information in data, leaving the level of meaningful
precision unassessed. Here we define the bitwise real information content from information theory
for the Copernicus Atmospheric Monitoring Service (CAMS). Most variables contain fewer than 7 bits
of real information per value and are highly compressible due to spatio-temporal correlation.
Rounding bits without real information to zero facilitates lossless compression algorithms and
encodes the uncertainty within the data itself. All CAMS data are 17× compressed relative to 64-bit floats,
while preserving 99% of real information. Combined with four-dimensional compression, factors beyond 60× are achieved.
A data compression Turing test is proposed to optimize compressibility while minimizing information
loss for the end use of weather and climate forecast data.

See 

- Klöwer M, M Razinger, JJ Dominguez, PD Düben and TN Palmer, 2021. *Compressing atmospheric data into its real information content*, **Nature Computational Science**, 1, 713-724, [10.1038/s43588-021-00156-2](https://doi.org/10.1038/s43588-021-00156-2)
