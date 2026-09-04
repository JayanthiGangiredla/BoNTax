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
# Galaxy Workflow for Sequence Analysis

This repository contains two versions of a Galaxy workflow, optimized depending on your input file format, along with a library of 46 reference genomes for alignment and querying.

##  Available Workflows

*   **FASTA Workflow (`galaxytrakr-workflow/Galaxy-Workflow-ClostBoNTax_FastA.ga`)**: Designed for assembled nucleotide sequences without quality scores.
*   **FASTQ Workflow (`galaxytrakr-workflow/Galaxy-Workflow-ClostBoNTax_FastQ.ga`)**: Designed for raw sequencing reads. Includes steps for quality control (QC) and trimming and assembly.

##  Input Requirements

| Workflow Version | Expected Input Format | Common File Extensions |
| :--- | :--- | :--- |
| **FASTA Version** | Standard FASTA | `.fasta`, `.fa`, `.fna`, `.faa` |
| **FASTQ Version** | Standard FASTQ (Sanger/Illumina 1.8+) | `.fastq`, `.fq`, `.fastq.gz` |

---
## How to Import the Workflows

1. Download the appropriate `.ga` file from the `galaxytrakr-workflows/` directory.
2. Log into your **Galaxy instance**.
3. Navigate to **Workflow** in the top menu and click **Upload or import workflow**.
4. Choose the downloaded `.ga` file and import it into your account.
## 🧬 Reference Genomes

This repository includes **46 compressed reference genomes** located in the `reference-db/` directory. All genomes are compressed in `.fasta.gz` format to optimize space and are natively compatible with Galaxy.
### How to use these references in Galaxy:
1. Download the specific `.fasta.gz` genome(s) you need from the `reference-db/` folder in this repository.
2. Upload the compressed file directly into your Galaxy history.
3. Create a dataset list of all reference genomes.
4. Select the list of uploaded reference file as your reference input dataset.
### Output QC_ANI_Results Report Fields

The workflow automatically generates an integrated QC, FastANI, AMR, toxin andd MLST report containing the following metrics:

| Field | Description |
| :--- | :--- |
| **Sample ID** | Unique identifier for the sample |
| **Genome size (bp / Mb)** | Total assembly size (expected 3.6 – 4.5 Mb) |
| **QC status (PASS / FAIL)** | Based on 3.6 – 4.5 Mb gate |
| **AMR profile** | Detected antimicrobial resistance genes (if any) |
| **Toxin presence (type & subtype)** | Detected neurotoxin marker(s) and subtype(s) (if any) |
| **MLST Schema** | PUBMLST Schema |
| **ST** | Sequence Type match|
| **Best reference hit** | Top matching reference species |
| **ANI (%)** | Average Nucleotide Identity (%) |
| **Aligned fragments** | Number of aligned fragments |
| **Total fragments** | Total number of fragments |
| **Species match** | *C. sporogenes* / *C. botulinum* group I / Unknown |

# Conclusion
* By integrating curated reference genomes and ANI-based species assignment with independent BoNT characterization, ClostBoNTax provides a reproducible framework for distinguishing closely related C. botulinum Group I and C. sporogenes lineages without conflating taxonomic identity with toxin-associated pathogenic potential
## Citation & Publication

A manuscript describing this workflow is currently **in preparation**.
* Authors : Gangiredla Jayanthi, Shashi Sharma, and Gonzalez-Escalona Narjol 
