# SingleBCell-FluVaccine

Analysis workflows for Horns et al. bioRxiv 2019.

These workflows were used to analyze the molecular, cellular, and population features of human B cells during the memory response to influenza vaccination. Data were collected using single-cell transcriptional profiling, single-cell paired heavy-light chain antibody sequencing (10X Genomics), antibody repertoire sequencing, and traditional antibody binding measurements (ELISA and biolayer interferometry). Results were published on bioRxiv in 2019 (https://www.biorxiv.org/content/10.1101/709337v1).

This repository contains Jupyter Notebooks that reproduce the figures shown in the paper.

## Configuration

### Environment
Python 2.7 is the primary environment. Python 3.7 is used for one notebook, `Transcriptome.ipynb`, which requires Scanpy. Complete Python environments are specified by YAML files in the repository, which can be used to create an environment using Anaconda.

### Data
Preprocessed data are used as inputs for these notebooks. They are available for download via Google Drive at XXX. The notebooks expect the data files to be found in the `data/` directory, so you can simply extract the archived data directly into `data/`.

## Contents

### `notebooks`

Each notebook is roughly associated with one or a few figures from the paper. More detailed descriptions of the analysis performed in each notebook are provided at the top of the notebook.

`Dynamics` ~ Figure 1

`PreprocessVDJ` ~ Figure S1

`Transcriptome` ~ Figure 2, Figure S2, Figure S3

`Tree_L3` ~ Figure 4

`Affinity` ~ Figure 4, Figure S5

`Competition` ~ Figure S6

Graphical outputs are written by default to `notebooks/outs/`.

### `data`

`Affinities.tsv`: Summary of binding affinity measurements performed by biolayer interferometry (on the ForteBio Octet instrument).

`all_contig_annotations.csv`: Annotation of assembled contigs from single-cell sequencing (output from 10X Genomics cellranger). 

`all_contig_annotations_igblast.txt`: Annotation of contigs filtered for contigs that belong to valid cells using IgBlast, which assigns V gene usage with allele-level resolution and reports identity to the reference V gene.

`all_contig_annotations.valid.csv`: Annotation of contigs filtered for contigs that belong to valid cells, which have exactly one productive heavy and one productive light chain contig.

`all_contig_annotations.valid.IGH.csv`: Annotation of contigs filtered for heavy chain contigs that belong to valid cells, which have exactly one productive heavy and one productive light chain contig.

`cell_annotations_contigs.csv`: Annotation of cells detected by single-cell sequencing with their highest confidence heavy and light chain contigs and features of those contigs.

`cell_annotations_dynamics.tsv`: Annotation of cells detected by single-cell sequencing with their clone dynamics (as measured by antibody repertoire sequencing).

`cell_ranger_metrics_summary.csv`: Summary metrics describing sequencing quality and various characteristics of detected single cells (output from 10X Genomics cellranger).

`clone_annotations_RepSeq.tsv`: Annotation of the molecular features of each B cell clone identified by antibody repertoire sequencing (VDJ gene usage).

`clone_dynamics.tsv`: Dynamics of B cell clones during a 16-day window before and after vaccination. Each row is a clone. Columns indicate the abundance of that clone at various visits (V1-8) corresponding to various days before and after vaccination. Abundances are given in terms of number of unique sequences (sequences_\*) or number of unique molecules (UMIs) (molecules_\*) belonging to the clone. Fractional abundances are also given (sequences_normed) (calculated by dividing number of sequences by the total number of sequences observed at the timepoint).

`contig_annotations_RepSeqMapping.tsv`: Annotation of contigs identified by single-cell sequencing based on their nearest match in the antibody repertoire sequencing data. In particular, to integrate single-cell sequencing results with antibody repertoire sequencing, we searched for the nearest sequence in the repertoire data using a custom algorithm (described further in STAR Methods) and the results of that search are reported here. Several molecular features of the nearest matching repertoire sequences are given.

`differential_expression_Loupe_ActivatedMemory_Memory.csv`, `differential_expression_Loupe_Memory_ActivatedMemory.csv`, `differential_expression_Loupe_Memory_Naive.csv`, `differential_expression_Loupe_Naive_Memory.csv`: Differential expression analysis between subsets of B cells (Activated Memory vs Memory, Memory vs Activated Memory, Memory vs Naive, and Naive vs Memory, respectively) performed in Loupe Cell Browser.

`filtered_gene_bc_matrices_h5.h5`: Transcriptional profiles of 36,501 single cells summarized as a gene-barcode matrix (output from 10X Genomics cellranger). Each element of the matrix is the number of UMIs associated with a feature (row) and a barcode (column). 

`gene_names_BCR_TCR.txt`: Names of BCR- and TCR-related genes. These genes were excluded from the transcriptome analysis in order to remove effects arising from VDJ usage (which potentially differs between the naive, memory, and activated memory subsets).

`L3_competition_kinetics.csv`: Raw data from epitope binning measurements by cross-competition between L3 antibodies. Measurements were performed by biolayer interferometry (on the ForteBio Octet instrument).

`L3.fasta`: Alignment of L3 antibody heavy chain DNA sequences.

`L3_germline_kinetics.txt`: Raw data from kinetic measurement of binding between L3_germline antibody and Influenza A HA performed by biolayer interferometry (on the ForteBio Octet instrument). 

`L3.nwk`: Phylogenetic tree of L3 antibody clone.

`L3_recombinant.fasta`: Alignment of L3 antibody heavy chain DNA sequences that were produced recombinantly.

`tsne_projection.csv`: t-distributed Stochastic Neighbor Embedding (tSNE) projection of the transcriptional profiles of 36,501 single cells into two dimensions.

## Disclaimer
This project is not maintained. Software is provided as is and requests for support may not be addressed.

## Contact
If you have questions or comments, please contact Felix Horns at rfhorns@gmail.com.
