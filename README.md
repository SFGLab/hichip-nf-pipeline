<h2 align="center"> nf-HiChIP Pipeline </h2>

<p align="center">
<img align="center" src="https://github.com/SFGLab/nf-hichip/blob/main/nf_HiChIP.png">
</p>

-------
## Introduction

We have developed an nf-HiChIP pipeline that combines the analytical approach designed for ChIP-seq data processing (mapping, filtering, peak calling, coverage tracks calculations) with HiChIP-specific analysis (MAPS pipeline, Juric, Ivan, et al.). This pipeline enables users to conduct thorough and efficient analysis of multiple HiChIP datasets simultaneously, eliminating the requirement for additional ChIP-seq experiments.

-------
## Install

#### Step 1.
[Docker](https://hub.docker.com/) image available:
```
https://hub.docker.com/repository/docker/mateuszchilinski/hichip-nf-pipeline/general
```
Command to pull Docker image:
```
docker pull mateuszchilinski/hichip-nf-pipeline
```
#### Step 2.
To use the pipeline, you need to have [Nextflow](https://www.nextflow.io/docs/latest/index.html) installed.

> To run, use the command: 

```
nextflow run main.nf --design design.csv
```
#### Step 3.
Example  for design.csv file:

sample | fastq_1 |fastq_2 | replicate |
-- | ------ |------ | ------ |
S1 | /data/SAMPLE1_1_R1.fastq.gz | /data/SAMPLE1_1_R2.fastq.gz | 1
S1 | /data/SAMPLE1_2_R1.fastq.gz | /data/SAMPLE1_2_R2.fastq.gz | 2
S2 | /data/SAMPLE2_1_R1.fastq.gz | /data/SAMPLE2_1_R2.fastq.gz | 1
S2 | /data/SAMPLE2_2_R1.fastq.gz | /data/SAMPLE2_2_R2.fastq.gz | 2

#### Step 4.
The parameters of the pipeline can be found in the following table. All of them are optional: 

Parameter | Description | Default |
-- | ------ |------ |
--ref | Reference genome for the analysis. | /workspaces/hichip-nf-pipeline/ref/Homo_sapiens_assembly38.fasta
--outdir | Folder with the final results. | results
--design | .csv file containing information about samples and replicates. | /workspaces/hichip-nf-pipeline/design_high.csv
--chrom_sizes | Sizes of chromosomes for the specific reference genome. | /workspaces/hichip-nf-pipeline/hg38.chrom.sizes
--threads | Threads to use in each task. | 4
--mem | Memory to use (in GB) for sorting task. | 4
--mapq | MAPQ for MAPS. | 30
--peak_quality | Quality parameter (q-value (minimum FDR) cutoff) for MACS3. | 0.05
--genome_size | Genome size string for MACS3. | hs

-------
## Citation
If you use nf-HiChIP in your research (the idea, the algorithm, the analysis scripts, or the supplemental data), please give us a star on the GitHub repo page and cite our paper as follows:    

- Official version  --
- Preprint bioRxiv --
-------
