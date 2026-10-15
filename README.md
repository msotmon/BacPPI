# BacPPI

BacPPI is a bioinformatic framework oriented to predict protein-protein interaction and the annotation of the unknown/unnanotated genes in eukaryotes.
The project combines the covariance co-evolution signal extracted from a Jacobian matrix (gLM2) with the genomic context and the transcriptomic co-expression.

## Goals 
1. **Prioritization of pairs**: Integrate operon structure and co-expression data of RNA-seq data to find the pairs with major biological interest.
2. **Covariance metric extraction**: Process in an HPC environment the gLM2 model to obtain descriptor of linkage such as `ìnter_max`,`inter_p99` and the relation of the monomeric folding (`ratio_inter_vs_intra`).
3. **Modelling and annotation**: Train a ML model to predict stable functional complexes and transfer that annotation to genes with unknown function ("Guilt by association")

## Project status
The project is currently in the phase of data preprocessing and large-scale feature extraction.

## Requirements and installation
### Clone the repo
``` bash
git clone [https://github.com/tu-usuario/BacPPI-GLM2.git](https://github.com/tu-usuario/BacPPI-GLM2.git) 
cd BacPPI-GLM2
``` 

### Create and activate conda enviroment
```
conda env create -f environment.yml 
conda activate bac_ppi_glm2
``` 

### Download the model
1. **Python** :
 ```
from huggingface_hub import snapshot_download 
snapshot_download( 
   repo_id="tattabio/OMG",  
   local_dir="models/tattabio",
   local_dir_use_symlinks=False
) 
  ```
2. **Git LFS** :
```
git lfs install
git clone [https://huggingface.co/tattabio/OMG](https://huggingface.co/tattabio/OMG) models/tattabio

```

## Acknowledges
We acknowledge the following entities and infrastructure for making the development of this work possible:

    GLM2 / TattaBio Models: TattaBio. Sequence-based representations and Jacobian metrics for protein interactions. Hugging Face Repository: https://huggingface.co/tattabio

    Supercomputing Infrastructure: The calculations and massive data processing were carried out using the computing resources of the Picasso supercomputer, which belongs to the SCBI (Supercomputing and Bioinnovation Center) at the University of Málaga (UMA).
