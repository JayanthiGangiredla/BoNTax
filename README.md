# BoNTax
a curated genome-based framework for taxonomic classification and characterization of Clostridium botulinum Group I and Clostridium sporogenes.
* This is a [Galaxy](https://galaxyproject.org/) formatted workflow.
# Workflow Overview
* Quality control and trimming with FastQC(Galaxy Version 0.74+galaxy1) and fastp(Galaxy Version 1.3.3+galaxy0)
* Genome assembly with SKESA(skesa / 0.24)
* Assembly quality assessment with QUAST(5.3.0+galaxy1)
* Toxin gene and AMR gene screening with AMRFinderPlus(4.2.5+galaxy2) db-12-25-03.1
* MLST Screening based on PUBMLST schema for Clostridium botulinum(2.22.0) db-2025-10-16
* Taxonomic comparison with FastANI(Galaxy Version 1.3) against reference genomes
* Visualization using ANI heatmap using ggplot2_heatmap2(Galaxy Version 3.3.0+galaxy0)
# Dependecies
* This workflow relies on external tools from the Galaxy ToolShed (https://toolshed.g2.bx.psu.edu/). They can be auto-installed via Ephemeris using the included [dependencies/tools.yml] (dependencies/tools.yml).
# Galaxy Workflow for Sequence Analysis

This repository contains two versions of a Galaxy workflow, optimized depending on your input file format, along with a library of 46 reference genomes for alignment and querying.

##  Available Workflow

* **FASTA Workflow (`galaxytrakr-workflow/BoNTax_FastA.ga`)**: Designed for assembled nucleotide sequences without quality scores.
* **FASTQ Workflow (`galaxytrakr-workflow/BoNTax_FastQ.ga`)**: Designed for raw sequencing reads. Includes steps for quality control (QC) and trimming and assembly.
---
## How to Import the Workflow

1. Download the appropriate `.ga` file from the `galaxytrakr-workflows/` directory.
2. Log into your **Galaxy instance**.
3. Navigate to **Workflow** in the top menu and click **Upload or import workflow**.
4. Choose the downloaded `.ga` file and import it into your account.

##  Input Requirements

| Workflow Version | Expected Input Format | Common File Extensions |
| :--- | :--- | :--- |
| **FASTA Version** | Standard FASTA | `.fasta`, `.fa`, `.fna`, `.faa` |
| **FASTQ Version** | Standard FASTQ (Sanger/Illumina 1.8+) | `.fastq`, `.fq`, `.fastq.gz` |
## 🧬 Reference Genomes

This repository includes **46 compressed reference genomes** located in the `reference-db/` directory. All genomes are compressed in `.fasta.gz` format to optimize space and are natively compatible with Galaxy.
### How to use these references in Galaxy:
1. Download the specific `.fasta.gz` genome(s) you need from the `reference-db/` folder in this repository.
2. Upload the compressed file directly into your Galaxy history.
3. Create a dataset list of all reference genomes.
4. Select the list of uploaded reference file as your reference input dataset.
### Output QC_ANI_Results Report Fields

The workflow automatically generates an integrated QC, FastANI, AMR, toxin and MLST report containing the following metrics:

| Field | Description |
| :--- | :--- |
| **Sample** | Unique identifier for the sample |
| **Total length (>= 0 bp)** | Genome size in base pairs (bp) |
| **# contigs** | Number of contigs in the assembly |
| **N50** | Length of the shortest contig accounting for 50% of the total assembly length |
| **QC_check** | Quality control check based on the 3.6 – 4.5 Mb genome size gate |
| **AMR** | Detected antimicrobial resistance genes (if any) |
| **VIRULENCE** | Detected neurotoxin marker(s) and subtype(s) (if any) |
| **ST** | Sequence type (ST)  |
| **MLST_Schema** | PUBMLST Schema specifically for *C. botulinum* |
| **Reference_match** | Top matching reference species |
| **ANI** | Average Nucleotide Identity (%) |
| **Aligned_Fragments** | Number of aligned fragments |
| **Total_Fragments** | Total number of fragments |
| **Species_match** | Final classification (*C. sporogenes* / *C. botulinum* group I / Unknown) |

# Conclusion
* By integrating curated reference genomes and ANI-based species assignment with independent BoNT characterization, ClostBoNTax provides a reproducible framework for distinguishing closely related C. botulinum Group I and C. sporogenes lineages without conflating taxonomic identity with toxin-associated pathogenic potential
## Citation & Publication

A manuscript describing this workflow is currently **in preparation**.
* Authors : Gangiredla Jayanthi, Shashi Sharma, and Gonzalez-Escalona Narjol 
