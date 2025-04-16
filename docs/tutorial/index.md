---
layout: default
title: Tutorial
nav_order: 3
---

# Tutorial

## Running Pipeline on Google Colab
The simplest way to use the Pipeline is using this [colab notebook](https://colab.research.google.com/github/luquelab/bioinformatics-teamwinners/blob/colab_dev/notebooks/sequence_analysis_pipeline.ipynb) which runs the pipeline on a free Google cloud-based platform in a Jupyter environment. The Colab notebook is self documenting and is designed to be simple to use. 

This quick-start guide is also included within the notebook.

## Colab quick-start guide
Follow these steps to obtain a comprehensive phylogenetic and functional analysis. To best navigate the guide, follow along in the Table of Contents in the notebook.
1. Input the sequences to be analyzed in the [Input structure](https://colab.research.google.com/github/luquelab/bioinformatics-teamwinners/blob/colab_dev/notebooks/sequence_analysis_pipeline.ipynb#scrollTo=Or6fjc0Fuw1r&line=53&uniqifier=1) section of the notebook. Run the code block to upload the structure file. If only interested in trying out the Pipeline, navigate to the `examples/` folder and download the file `tutorial_sequences.fasta` to use as an input.
2. Execute the rest of the notebook by navigating the Colab menu `Runtime` and choosing the option `Run all`. This will install all the necessary packages, run the pipeline, and generate and store the results in the appropriate folders.
  + The execution time might depend on the computing power and memory of the Colab cloud service used, which depends on the user's Colab plan. It is expected to take around 25 minutes due to the BLAST searchers taking a long time.
3. To see the results, download all the files and folders outputted by the code.
