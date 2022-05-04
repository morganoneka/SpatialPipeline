# Spatial Cell Patterns Pipeline
Here are tutorials covering a few key elements of my work studying spatial relationships between cell types! These workflows are intended for usage with data that A) has spatial X/Y coordinates, and B) has a discrete notion of cell type.

To learn more about applications, see [my website](morganoneka.github.io/).

Data is the CODEX data used in [this paper](https://www.sciencedirect.com/science/article/pii/S0092867420308709), split by patient.

## Density
We use [spatstat](https://spatstat.org/) to calculate the density of a cell type within a sample, using a fixed grid width so that samples can be compared. Densities can be useful for a lot of downstream analysis; I've used this output to find [diagnostically relevant regions](https://github.com/morganoneka/DensityAttention) using image-based machine learning methods.

## Gcross
In this workflow, we convert our data to a point pattern process (using spatstat), run Gcross, analyze the AUC, and compare the Gcross curve to theoretical.

## Giotto
Using [Giotto](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-021-02286-2), an R package intended for spatial -omics data, we identify pairs of cells that tend to cluster together ("enriched" cell pairs) and pairs of cells that tend to be distant from one another ("depleted" cell pairs).
