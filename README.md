# bioinformatics-teamwinners🦧
This is the group project for the bioinformatics Tools course for Team (bread)winners: Jose-Bernard Sedalo, Izzy Childress, Miya Khoo, and Maria V Naffah

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

For the next part of the process, I used AlphaFold to obtain the folded protein structures. I did this by inputting each of the translated protein sequence strings in FASTA format. I saved each top result as a
.cif file. I then imported the .cif files into Chimera to compare the 6 protein structures. I used the Matchmaker tool to orient the proteins into positions that most resembled each other. Using the tile function, I was able to view all the proteins alongside each other.

I had significant issues trying to use Foldseek inside the Chimera application. So, I used Foldseek in browser. Unfortunately, this means I was not able to emulate code for that part of the process. I will instead describe the process below:
1. Upload each .cif file one by one to search the proteins in their folded form.
2. Use the results to draw conclusions!

I did not understand what was meant by the pairwise homologies. And I'm sure you guys explained it to me multiple times. I am sorry, that is my fault.
