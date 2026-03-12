# Single Cell Analysis Pipeline

#### Quality Control: 
Includes **%mt(Mitochondrial) gene Filtering**, **%rRNA(Ribosomal) gene filterig**, **doublet detection and filtering**, **Highly Variable Genes(HVG) filtering** and **data normalization** done using [scanpy](https://scanpy.readthedocs.io/en/latest/) and [SCVI](https://scvi-tools.org/).
 
 
**Basic pre-processing of Data**
- Data quality control can be split into cell QC and gene QC. - Typical quality measures for assessing the quality of a cell include the number of molecule counts (UMIs), the number of expressed genes, and the fraction of counts that are mitochondrial.
- A high fraction of mitochondrial reads being picked up can indicate cell stress, as there is a low proportion of nuclear mRNA in the cell.
- It should be noted that high mitochondrial RNA fractions can also be biological signals indicating elevated respiration.

#### Dimensionality Reduction: 
Includes **PCA**, **UMAP**, and **t-SNE** done using scanpy's `sc.tl.pca()`,`sc.tl.umap()` and `sc.tl.tsne()` functions.

#### Canonical Correlation Analysis (CCA):
Includes **Leiden Clustering with Resolution Optimization** and  **Alternative Clustering Methods** alongside comparison of both clustering methods were shown

#### Differential Expression Analysis:
Includes **Finding Marker Genes**, **Cell Type Annotation**, and **Automated Annotation with CellTypist**.

#### Downstream Analysis:
Differential gene expression (DGE) analysis is a crucial tool for identifying genes that are significantly over or underexpressed between different conditions (e.g., healthy vs. disease) within specific cell types.

While many tools exist for DGE analysis, recent studies suggest that pseudobulk methods (which aggregate cell-type-specific expression values per individual) perform particularly well for single-cell data, helping to avoid issues like pseudoreplication and inflated false discovery rates.


Primarily used the packages `decoupleR` and `pybiomart` for gene symbol conversion.


Includes **Generating Pseudobulks**, **Aligning gene identifiers**, **Assessing the quality of our pseudo-bulks**, **Denoising the pseudo-bulks**, **Differential expression analysis of the pseudo-bulks using `pydeseq2`**, **Visual inspection of differentially expressed genes**, and **Enrichment with Over Representation Analysis (ORA)**.


## Deep Learning (DL) Applications in Single-Cell Analysis
Includes **Loading Scanpy built-in dataset (PBMC3k)**, **Representation learning + denoising using ([scVI](https://scvi-tools.org/))**,  **Batch correction / integration (scVI with batch)**, **Cell type annotation (semi-supervised) with scANVI**, and **Trajectory / pseudotime on DL latent using scVI latent**.
