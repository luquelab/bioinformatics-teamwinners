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

# Overall process
1. Uploading necessary starting materials
Install BioPython.
Upload the provided file called sequences.fna and set it equal to sequences_path so the file path doesn't have to be repasted into future code.
Import SeqIO and parse the fasta file.

2. Analyzing sequence properties
Parse the sequences.fna file to extract the sequence lengths and their GC values.
Graph the values using Matplot.

3. Translating the sequences
Set your translation_table to = 11
Set the translated_seq equal to seq_record.seq.translate to translate the sequence
Create a new SeqRecord for thr transated sequence and save it to a new file

4. Sequence alignment
Import the necessary libraries/materials and install Mafft.
Use Mafft to execute the alignment and parse the output uing StringIO
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
Convert the translated sequences into list format.
Import the necessary libraries and materials.
Conduct a BLAST query defining the following parameters: Bio.SeqRecird object (your sequence), type of BLAST program, database, hitlist size, output directory.

8. Making predictions using Hidden Markov Models
Use the list formatted sequences to conduct a HMMR query defining the following parameters:BioSeq object (protein sequence), sequence identifier, database, output directory.

9. Define your pipeline (performing the BLAST and HMMR queries on each sequence), using the format:fasta_file = INPUT_FASTA, out_dir = OUTPUT_DIR. This will run the pipeline for each sequence and save the domain, organism, and function predictions to CSV files.
Use the results to create the data frames.
Execute the pipeline!