# DNA Sequencing Data Analysis (Variant calling) Pipeline
This repository contains a Bash script for preprocessing DNA sequencing data and performing variant calling analysis using GATK (Genome Analysis Toolkit).

# 1. Preprocessing Steps

#### 1. Download Reference File: Downloads the reference genome (hg38) in FASTA format and unzips it.
#### 2. Index Reference File: Indexes the reference genome using samtools faidx.
#### 3. Create Sequence Dictionary: Creates a sequence dictionary for the reference genome using GATK.
#### 4. Mark Duplicates: Identifies and marks duplicate reads in BAM files using GATK's MarkDuplicates tool.
#### 5. Sort BAM Files: Sorts the BAM files by genomic coordinates using GATK's SortSam tool.
#### 6. Index Sorted BAM Files: Indexes the sorted BAM files using samtools index.

## Optional Steps (Base Recalibration)
Uncomment and run these steps if base quality score recalibration (BQSR) is required:

#### 7. Base Recalibration (BQSR): Performs base quality score recalibration using GATK's BaseRecalibrator and ApplyBQSR tools.

# 2. Variant Calling

#### 1. Download Germline Mutation Filtering Resource: Downloads the gnomAD germline variant resource (hg38) for filtering germline variants.
#### 2. Variant Calling on Cancer Samples: Calls variants using GATK's Mutect2 caller on cancer samples with gnomAD germline resource.
#### 3. Filtering Germline Variants: Filters germline variants using GATK's FilterMutectCalls tool.

# 3. Annotation and Filtering

#### 4. Annotate Variants: Annotates variants with functional information using GATK's Funcotator tool.

#  Other Information

##### 1. The pipeline assumes the availability of necessary reference files and software tools such as GATK and samtools.
##### 2. The pipeline is designed to process cancer sequencing data (tumor samples).
##### 3. Detailed comments are provided within the script to explain each step.
##### 4. Optional steps can be uncommented and modified as needed.
##### 6. Runtime duration is calculated and displayed at the end of the script.

# Execution

##### 1. Clone this repository.
##### 2. Ensure all necessary reference files and software tools are available.
##### 3. Modify file paths and parameters as needed.
##### 4. Execute the script.
