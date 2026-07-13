# Rhizosphere miRNA Analysis

This repository contains the analysis of rhizosphere miRNA sequencing data following the miRDeep2 pipeline for soil small RNA sequencing.

The dataset includes four plant species:

* Wheat
* Corn
* Soybean
* Common bean

Each species contains two genotypes.

## Scripts

### Script 1

* Load required R packages.
* Import raw data.
* Clean the raw data, including the removal of duplicate miRDeep2 predictions.
* Match sequences to their corresponding `read_ID`.
* Add metadata from the mapping file.

### Script 2

Generate heatmaps to visualize read abundance in both plant and no-plant samples.

### Script 3

Annotate miRNAs using the miRBase mature miRNA database.

* Sequences are preferentially matched to miRNAs from the corresponding plant species.
* If no exact match is found, sequences with up to 3 mismatches are annotated.
* `iso-` is added to the miRNA name for putative isomiRs.
* `ho-` is added for homologous miRNAs originating from another species.

### Script 4

Generate boxplots of raw and normalized miRNA counts for plant and no-plant samples.

### Script 5

Perform PCA on miRNA abundance data using a Hellinger transformation.

* First, miRNAs detected in no-plant samples are removed.
* The remaining no-plant control samples are then excluded.
* The four species-specific datasets are combined before PCA.

### Script 6

Perform differential expression analysis of miRNA counts using DESeq2.

### Script 7

Generate:

* Boxplots of miRNA abundance for each species.
* Heatmaps showing the presence/absence of miRNA sequences.
* Heatmaps of miRNA families.

### Script 8

Perform a Mantel test to assess the correlation between miRNA community composition and rhizosphere bacterial community composition.

### Script 9

Construct and compare plant species and miRNA phylogenetic trees using a cophylogenetic analysis.

*A plant phylogeny is generated from chloroplast marker gene sequences alignements.
*A miRNA tree is generated from jaccard distance 
*Both tree use neighbour joining
*The two trees are visualized as a cophylogenetic plot (cophylo).
