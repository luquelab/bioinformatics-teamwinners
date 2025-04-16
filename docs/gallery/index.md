---
layout: default
title: Gallery
nav_order: 4
---

# Gallery of Results
This bioinformatics pipeline investigates mystery sequences. It contains a complete workflow to analyze unknown DNA sequences using sequence-level analysis and will characterize unknown nucleotide sequences provided as input, predict their function, origin, and relationships. The following are some of the outputs created by the notebook to analyze the sequences. 

## Alignments
Calculated sequence properties like sequence length and GC content. Translated nucleotide sequences to proteins and performed pairwise alignments for nucleotide and protein sequences.
![1](sequence_properties.png)
![2](nucleotide_similarity.png)

## Functional prediction
Predicted functional domains using HMMER + Pfam.

```
BLAST Results for Sequence_1

Hit: heat shock protein 60A [Cherax quadricarinatus] >ref|XP_069948245.1| heat shock protein 60A [Cherax quadricarinatus] >gb|AKB96206.1| heat shock protein [Cherax quadricarinatus] >gb|KAK8738990.1| hypothetical protein OTU49_003777 [Cherax quadricarinatus] >gb|QIB00648.1| heat shock protein [Cherax quadricarinatus]
E-value: 0.00e+00
Organism: Cherax quadricarinatus

Hit: heat shock protein [Cherax cainii]
E-value: 0.00e+00
Organism: Cherax cainii

Hit: heat shock protein [Cherax destructor] >gb|WLO59330.1| heat shock protein 60 [Cherax destructor]
E-value: 0.00e+00
Organism: Cherax destructor

Hit: heat shock protein 60A [Procambarus clarkii]
E-value: 0.00e+00
Organism: Procambarus clarkii

Hit: heat shock protein 60A-like [Panulirus ornatus]
E-value: 0.00e+00
Organism: Panulirus ornatus
```

## Organism prediction
Predicted organism of origin using BLAST-like homology.
![1](organism_predictions.png)
![2](domain_predictions.png)

## Phylogenetic tree
Constructed phylogenetic trees from similarity matrices.
![1](tree_nucleotides.png)
![2](tree_proteins.png)
