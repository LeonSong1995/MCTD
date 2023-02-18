---
layout: full
homepage: true
disable_anchors: true
description: MeDuSA
---
## CARD Overview
![iDEA\_pipeline](Overview1.jpg)
MeDuSA is a fine-resolution cellular deconvolution method that leverages scRNA-seq data as a reference to estimate cell-state abundance in bulk RNA-seq data. MeDuSA features the use of a linear mixed model (LMM) to fit a cell state in question (either a single cell or the mean of multiple cells) as a fixed effect and the remaining cells of the same cell type individually as random effects accounting for correlations between cells. This model improves the deconvolution accuracy because the random-effect component allows each cell has a specific weight on bulk gene expression, resulting in a better capturing of variance in bulk gene expression. This model aslo ameliorates the collinearity problem between cells at the focal state (fitted as a fixed effect) and those at adjacent states (fitted as random effects) because of the shrinkage of random effects.

### Example Analysis with CARD: [here](https://yingma0107.github.io/CARD/documentation/04_CARD_Example.html).