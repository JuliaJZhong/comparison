# Comparison of B cell transcriptomes

This is the code that I used to do some preliminary analysis and comparisons between three datasets:

1. [GSE242931](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSM7775222) from Kuehn et al. (2024) 
2. [GSE12366](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi) from Longo et al. (2009)
3. Unstimulated B cells from Christine's cytokine experiments

This code is a bit messy and by no means complete. I'd like to get around to working on it again, but in the meantime perhaps what I have now may be helpful to you!

## Files
I've only included the contents of src/ in this repository, but this is what the overall structure of my project directory looks like:
```
├── LICENSE
├── README.md
├── annotations                               # various annotation files I found online for mapping ENSEMBL IDs to gene symbols in Python, for 
│   ├── BCR_signaling.txt                     # from [here](https://amigo.geneontology.org/amigo/term/GO:0050853?relation=regulates)
│   ├── ensGtp.txt
│   ├── ensemblSource.txt
│   ├── ensemblToGeneName.txt
│   ├── gencode.v46lift37.annotation.gtf
│   ├── hg19.ensGene.gtf
│   ├── hg19.knownGene.gtf
│   └── hg19.refGene.gtf
├── kuehn_data
│   └── GSE242931_genematrix.txt              # kuehn counts matrix
├── longo_data
│   ├── GSE12366_genematrix.txt               # generated from the raw .CEL files in longo_processing.Rmd
│   ├── GSM310429.CEL
│   ├── GSM310430.CEL
│   ├── GSM310431.CEL
│   ├── GSM310432.CEL
│   ├── GSM310433.CEL
│   ├── GSM310434.CEL
│   ├── GSM310435.CEL
│   ├── GSM310436.CEL
│   ├── GSM310437.CEL
│   ├── GSM310438.CEL
│   ├── GSM310439.CEL
│   └── GSM310440.CEL
├── src
│   ├── combined_heatmap.ipynb               # combined kuehn and wiggins datasets with chaotic giant hierarchical heatmap
│   ├── kuehn_heatmap.ipynb                  # data loading and visualization code for kuehn dataset alone
│   └── longo_processing.Rmd                 # preprocessing of longo dataset
└── wiggins_data
    └── 4h_complete_counts_matrix.csv       # wiggins counts matrix
```
