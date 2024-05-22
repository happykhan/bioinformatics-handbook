---
title: Quality control criteria for genome assemblies
---

Go back to [A framework for quality control](01-qc-framework.md)


oh no 

## Contiguity (Genome assembly)
This measures how contiguous the assembled genome is. You can look at metrics like the `N50` and `L50`, which indicate the length of the longest contig and the number of contigs needed to cover a certain percentage of the genome. Higher `N50` and lower `L50` values are generally better. How can we assess contiguity?

* Less contigs, Longer contigs
* N50, average contig length, number of contigs etc.
* Try [QUAST](https://quast.sourceforge.net/quast.html)




## Completeness (Genome assembly)
You can assess genome completeness by comparing your assembly to a reference genome if available. How can we assess completeness?

* Compare to reference genome (How to find a reference genome? Start with [web BLAST](https://blast.ncbi.nlm.nih.gov/Blast.cgi))
* Use QUAST to compare to reference genome via different metrics, or align the two genomes and inspect via [Mauve](https://darlinglab.org/mauve/mauve.html) or [Artemis](https://www.sanger.ac.uk/tool/artemis/).
* Assume a genome should have single copy essential genes:
    * [MLST](https://github.com/tseemann/mlst) intact?
    * [BUSCO](https://busco.ezlab.org/) panel
    * [CheckM](https://ecogenomics.github.io/CheckM) panel

## Contamination (Genome assembly)

Some common reasons for contamination in sequencing data include:

* Sample Cross-Contamination
* Contaminated Reagents and Kits
* Environmental Contamination
* Human Contamination
* Cross-Talking in Multiplexed Sequencing
* Lab Equipment Contamination
* Library Preparation and PCR Artifacts
* Sample Mix-Up

Check for contamination with tools like [Kraken/Bracken](https://ccb.jhu.edu/software/bracken/)

## Correctness (Genome assembly)

Assess the accuracy of your assembly by checking for misassemblies, such as structural errors, inversions, or translocations. Visualization tools like Artemis or Bandage can help identify such issues. Effectively we are trying to assess, is the genome assembly what we expect? How can we assess correctness?

* Assembly free from errors
* Mis-joins
* Collapsed repeats
* Duplication artefacts 
* False SNPs, InDels
* Comparison to Other Assemblies: If other assemblies of the same species are available, compare your assembly to them to identify any discrepancies. Ideally to well known reference genome.
* Map original reads back to assembled contigs
* Evaluation of Plasmids: If the bacterium has plasmids, confirm that they are correctly assembled and identify their sequences.
* Structural rearrangement tools - [Socru](https://github.com/quadram-institute-bioscience/socru)
* Try looking at the graph in [Bandage](https://rrwick.github.io/Bandage/)


## BONUS: Circumstantial (Genome assembly)

These are not direct evidence of a good genome, but can be reassuring.

What are some circumstanial evidence of a good genome?

* **GC Content:** Verify that the GC content of your assembly matches the expected GC content for the species. Significant deviations could indicate contamination or assembly errors.
* **Repeat Content:** Assess the presence and handling of repetitive elements. High levels of repeats may lead to fragmented assemblies or misassemblies.
* **Quality of Reads:** Examine the quality of the raw sequencing reads to ensure that they are of high quality, with minimal errors or biases.
* **Coverage Depth:** Evaluate the coverage depth across the genome. Uniform coverage indicates a more reliable assembly.
* **Visualization:** Use genome visualization tools like Artemis, IGV, or Tablet to visually inspect the assembly and confirm its quality.

Remember that the quality of your bacterial genome assembly may also depend on the sequencing technology used, the software and parameters employed for assembly, and the quality of the source DNA. Careful evaluation and validation of your assembly are essential for accurate results.
