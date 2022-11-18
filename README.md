# MeDuSA: mixed model-based deconvolution of cell-state abundance.

**Author: Liyang Song <songliyang@westlake.edu.cn>**    


## Description
MeDuSA is a fine-resolution cellular deconvolution method, with the aim to use reference scRNA-seq data to estimate the cell-state abundance of bulk RNA-seq data.

![Image text](https://github.com/LeonSong1995/MeDuSA/blob/master/schematic/schematic.jpg)

## Installation
```R
#Please install the Seurat first. (https://satijalab.org/seurat/)
install.packages("Seurat")

#R version > 3.5.0
if (!requireNamespace("devtools", quietly = TRUE))
    install.packages("devtools")
devtools::install_github("LeonSong1995/MeDuSA", build_vignettes=F)
```


## Usage
The function for **cell-state abundance** deconvolution in this package is `MeDuSA`, which needs:  
1. Bulk RNA-seq data.  A matrix of bulk RNA-seq data. Each row corresponds to a specific gene and each column corresponds to a particular sample.
2. Single-cell RNA-seq data. A [Seurat](https://satijalab.org/seurat/) obejct of the reference scRNA-seq data. 

## Example
MeDuSA package provides test data to show how to use.
```R
#Library the package
library(MeDuSA)

#Load the test data:
data(ref)
data(cellType)
data(cellTrajectory)
data(bulk)

#Build the 'Seurat' obejct:
sce = CreateSeuratObject(ref)
sce$cell_type = cellType
sce$cell_trajectory = rep(0,ncol(sce))
sce$cell_trajectory[rownames(Trajectory)]=Trajectory

#Run MeDuSA (2 cpu):
csab = MeDuSA(bulk=bulk,sce=sce,select.ct='Epithelium',ncpu=2)

#Documents
help(MeDuSA)
```

## Errors
The following errors mean that the MeDuSA model can not converge on your data. When you see them, you may need to check the signature genes or the reference scRNA-seq data.  
`REML ERROR!:V matrix is not positive.`  
`REML ERROR!: the X^t * V^-1 * X matrix is not invertible,please check the Signature Genes.`


## Contact
If you have any questions for MeDuSA, please contact the author <songliyang@westlake.edu.cn>.   
