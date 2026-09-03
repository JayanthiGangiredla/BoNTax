# ClostBoNTax
a curated genome-based framework for taxonomic classification and characterization of Clostridium botulinum Group I and Clostridium sporogenes.
* This is a [Galaxy](https://galaxyproject.org/) formatted workflow.
# Workflow Overview
* Quality control and trimming with FastQC and fastp
* Genome assembly with SKESA
* Assembly quality assessment with QUAST 
* Toxin gene and AMR gene screening with AMRFinderPlus
* MLST Screening based on PUBMLST schema for Clostridium botulinum
* Taxonomic comparison with FastANI against reference genomes
* Visualization using ANI heatmap using heatmap2
# Dependecies
* This workflow relies on external tools from the Galaxy ToolShed (https://toolshed.g2.bx.psu.edu/). They can be auto-installed via Ephemeris using the included tools.yml

# Conclusion
* By integrating curated reference genomes and ANI-based species assignment with independent BoNT characterization, ClostBoNTax provides a reproducible framework for distinguishing closely related C. botulinum Group I and C. sporogenes lineages without conflating taxonomic identity with toxin-associated pathogenic potential
## Citation & Publication

A manuscript describing this workflow is currently **in preparation**.
* Authors : Gangiredla Jayanthi, Shashi Sharma, and Gonzalez-Escalona Narjol 
