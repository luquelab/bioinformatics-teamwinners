# Here is a sample file directory:jdfsk
phylo_analysis_project/
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

# Inputs
``` nucleotide_sequence_path =  "/content/sequences.fna" #input file paths ```

Provide your nucleotide sequences file path.
The sequences file must contain at least two sequences because at least two sequences are required to to do a sequence alignment, which compares sequences to one another. This file must contain nucleotide sequences and be a .fasta or .fna file.

# Overall process
1. Upload necessary starting materials (see inputs above)


2. Analyze sequence properties
Parse the sequences.fna file to extract the sequence lengths and their GC values.
Graph the values using Matplot.

3. Translate the sequences
Set the translated_seq equal to seq_record.seq.translate to translate the sequence.
Create a new SeqRecord for the transated sequence and save it to a new file.

4. Sequence alignment
Import the necessary libraries/materials and install Mafft.
Use Mafft to execute the alignment and parse the output using StringIO.
Save the alignment to a file, then repeat this process for the protein alignment.

5. Similarity estimations
Load in the BLOSUM62 substitution matrix.
Load in the nucleotide and the protein alignments.
Calculate the similarity scores and save them to a CSV file.
Compute the distance matrix.

6. Creating a phylogenetic tree
Import Phylo and other necessary materials.
Create a DistanceTreeConstructor object.
Construct the phylogenetic tree.

7. Making predictions using BLAST
``` def calculate_similarity(dist_matrix, alignment, output_csv):
    similarity_matrix = 1 - dist_matrix
    np.fill_diagonal(similarity_matrix, np.nan)
``` 
Convert the translated sequences into list format. This must be done so the information can be interpreted by BLAST.
Import the necessary libraries and materials.
Conduct a BLAST query defining the following parameters: Bio.SeqRecird object (your sequence), type of BLAST program, database, hitlist size, output directory.

8. Making predictions using Hidden Markov Models
Use the list formatted sequences to conduct a HMMR query defining the following parameters:BioSeq object (protein sequence), sequence identifier, database, output directory.

9. Define your pipeline (performing the BLAST and HMMR queries on each sequence), using the format:fasta_file = INPUT_FASTA, out_dir = OUTPUT_DIR. This will run the pipeline for each sequence and save the domain, organism, and function predictions to CSV files.
Use the results to create the data frames.
Execute the pipeline!
