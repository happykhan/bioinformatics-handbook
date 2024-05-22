---
title: Practical - Genome assembly QC
---
 Here we will look at some genomes and assess their quality. Most of these genomes have (in my opinion) have quality issues. Remember that we are looking to as perfect reconstruction to the original genome, and we can assess this in different ways: 

* Contiguity
* Correctness
* Completeness
* Contamination

## Assessing genome assembly quality

The exercise is to download some assembled draft genomes and assess if they pass routine quality control. *The genomes are available at [https://zenodo.org/records/10018484](https://zenodo.org/records/10018484)*. 
You can directly download them with `wget` or similar. 

```
wget -O additional_genomes_for_qc.zip https://zenodo.org/records/10018484/files/additional_genomes_for_qc.zip?download=1
```

The files are FASTA (they are plain text) inside the zip file. There are eight genomes. Each FASTA file will look something like this. There will be multiple contigs, one after the other. Each with a fasta header (`>NODE_XXXX`) followed by the nucleotide sequence (`ATGC`).

```
>NODE_126_length_2252_cov_16.6409_ID_251
CAGCGTGGACTGATGTTCAG......
>NODE_22_length_135487_cov_12.0245_ID_43
GGCCGAGGCTCCCCACCGGCGCGGG....
>NODE_68_length_16957_cov_12.5198_ID_135
TGGTGTTGGTGCCAACGGCCTGACC...
>NODE_16_length_182200_cov_11.9821_ID_31
GCCGCTTTTTCGCGTTGCTTAATCT...
```

## Exercise 1: Assessing genome assembly quality

**Try to create a table of your assessment (with better explanations)** like the one below:

| Sample name | Pass/Fail | Reason |
|-------------|-----------|--------|
| sample_1    |  Yes  |     |
| sample_2    |  No         |        |
| sample_3    | Maybe          |        |
| sample_4    | I don't know         |        |
| sample_5    | Could you repeat the question?          |        |
| sample_6    |         |        |
| sample_7    |           |        |
| sample_8    |           |        |

This exercise is open-ended, and you can use any tools you like. You can use the tools we have used in the previous section, or you can try other tools. You can work in groups, or divide the different criteria between yourselves.

[Answers to exercises](/seq-analysis/check-qc-answers/)

[Back to Programme]({{site.baseurl}}/modules/sequence-analysis/programme/).