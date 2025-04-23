# About this Repository
Our pipeline focuses on phylogenetic and functional analysis of protein-coding sequences. Starting with a FASTA file of nucleotide sequences, the workflow handles everything from sequence translation and multiple sequence alignment to phylogenetic tree construction and functional annotation using BLAST and HMMER. Along the way, it also provides useful visualizations and summary files to help interpret the results. We’ve designed the project to be both educational and practical, which is ideal for students learning about comparative genomics or researchers who need a quick way to process and analyze protein sequences. The entire pipeline runs from a single Jupyter Notebook and is organized to clearly show each step, with outputs saved in a structured directory format.

# Here is a sample file directory:jdfsk
``` phylo_analysis_project/
|
|–– README.md
|–– bin/
|   └── analysis_pipeline.ipynb              # Jupyter Notebook driving the workflow
|
|–– data/
|   └── sequences.faa                        # amino_acid_sequence_path
|
└── results/
    ├── alignments/
    |   ├── nucleotide_alignments.aln        # nucleotide_alignment_path
    |   └── protein_alignments.aln           # protein_alignment_path
    |
    ├── phylogenetic_tree/
    |   ├── tree_nucleotides.nwk             # nucleotide_tree_path
    |   ├── tree_nucleotides.png             # nucleotide_tree_image
    |   ├── tree_proteins.nwk                # protein_tree_path
    |   └── tree_proteins.png                # protein_tree_image
    |
    └── functional_prediction/               # functional_prediction_path
        └── (prediction files …)          
```
# Inputs
``` nucleotide_sequence_path = os.path.join(base_path, "sequences.fna")  # input file paths```

Provide your nucleotide sequences file path.
The sequences file must contain at least two sequences because at least two sequences are required to to do a sequence alignment, which compares sequences to one another. This file must contain nucleotide sequences and be a .fasta or .fna file.

```
base_path = "/content"  # Can be changed to any directory, e.g., "/home/user/data"
```
The base bath can be reconfigured here, allowing th notebook to be downloaded and run without a hustle.
# Overall process
1. Upload necessary starting materials (see inputs above)


2. Analyze sequence properties
Parse the sequences.fna file to extract the sequence lengths and their GC values.
Graph the values.

3. Translate the sequences
Translate the sequences in frame one only.

4. Sequence alignment
Both nucleotide sequences and protein sequences are aligned using the Mafft algorithm.
Execute the alignment and parse the output.
Save the alignment to a file, then repeat this process for the protein alignment.

6. Similarity estimations
Load in the BLOSUM62 substitution matrix.
Load in the nucleotide and the protein alignments.
Calculate the similarity scores and save them to a CSV file.
Compute the distance matrix.

7. Create a phylogenetic tree
Construct the phylogenetic tree for nucleotide sequences and amino acid sequences.

8. Make predictions using BLAST and Hidden Markov Models

10. Define your pipeline (performing the BLAST and HMMR queries on each sequence), using the format:fasta_file = INPUT_FASTA, out_dir = OUTPUT_DIR. This will run the pipeline for each sequence and save the domain, organism, and function predictions to CSV files.
Use the results to create the data frames.
Execute the pipeline!

# GitHub Pages
Our [Pages](https://luquelab.github.io/bioinformatics-teamwinners/) site is connected to this repository and includes information about our pipeline and how to best run it.
