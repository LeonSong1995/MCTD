# MeDuSA: mixed model-based deconvolution of cell-state abundances.

## Overview
![Image text](https://github.com/LeonSong1995/MeDuSA/blob/master/docs/Overview2.jpg)

**MeDuSA** is a fine-resolution cellular deconvolution method that leverages scRNA-seq data as a reference to estimate `cell-state abundance` in bulk RNA-seq data. **MeDuSA** features the use of a linear mixed model (LMM) to fit a cell state in question (either a single cell or the mean of multiple cells) as a fixed effect and the remaining cells of the same cell type individually as random effects accounting for correlations between cells. This model improves the deconvolution accuracy because the random-effect component allows each cell has a specific weight on bulk gene expression, resulting in a better capturing of variance in bulk gene expression. This model aslo ameliorates the collinearity problem between cells at the focal state (fitted as a fixed effect) and those at adjacent states (fitted as random effects) because of the shrinkage of random effects.

## Installation
```R
# Please install the Seurat. (https://satijalab.org/seurat/)
install.packages("Seurat")

# Please install the BiocParallel. (https://bioconductor.org/packages/release/bioc/html/BiocParallel.html)
if (!require("BiocManager", quietly = TRUE))
    install.packages("BiocManager")
BiocManager::install("BiocParallel")

# Install the MeDuSA (R version > 3.5.0)
if (!requireNamespace("devtools", quietly = TRUE))
    install.packages("devtools")
devtools::install_github("LeonSong1995/MeDuSA", build_vignettes=F)
```


## Usage
See [tutorial] (https://leonsong1995.github.io/MeDuSA/)

## Contact
If you have any questions for MeDuSA, please contact the author <songliyang@westlake.edu.cn>.   
