# SingleBCell-FluVaccine

Analysis workflows for Horns et al. bioRxiv 2019.

These workflows were used to analyze the molecular, cellular, and population features of human B cells during the memory response to influenza vaccination. Data were collected using single-cell transcriptional profiling, single-cell paired heavy-light chain antibody sequencing (10X Genomics), antibody repertoire sequencing, and traditional antibody binding measurements (ELISA and biolayer interferometry). Results were published on bioRxiv in 2019 (https://www.biorxiv.org/content/10.1101/709337v1).

This repository contains Jupyter Notebooks that reproduce the figures shown in the paper.

## Configuration

### Environment
Python 2.7 is the primary environment. Python 3.7 is used for one notebook, `Transcriptome.ipynb`, which requires Scanpy. Both environments are specified by YAML files in the repository, which can be used to create an environment using Anaconda.

### Data
Preprocessed data are used as inputs for these notebooks. They are available for download via Google Drive at XXX. The notebooks expect the data files to be found in the `data/` directory.

## Contents

### `notebooks`

Each notebook is roughly associated with one or a few figures from the paper.

`Dynamics` ~ Figure 1

`PreprocessVDJ` ~ Figure S1

`Transcriptome` ~ Figure 2, Figure S2, Figure S3

`Tree_L3` ~ Figure 4

`Affinity` ~ Figure 4, Figure S5

`Competition` ~ Figure S6

Graphical outputs are written by default to `notebooks/outs/`.

## Disclaimer
This project is not maintained. Software is provided as is and requests for support may not be addressed.

## Contact
If you have questions or comments, please contact Felix Horns at rfhorns@gmail.com.
