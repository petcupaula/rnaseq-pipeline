# rnaseq-pipeline

## Download the files

### Option 1: SRA Toolkit

Download SRA Toolkit: https://trace.ncbi.nlm.nih.gov/Traces/sra/sra.cgi?view=software

Unarchive and configure (change workspace directory as described here: https://trace.ncbi.nlm.nih.gov/Traces/sra/sra.cgi?view=toolkit_doc&f=std):

```
cd bin
./vdb-config -i
```

```
./fastq-dump -v --gzip SRR1554537
```

The download is very time consuming (for example, retrieving SRR1554537 took 5 hours -- started 08:12:26 ended: 13:13:40). Therefore, going for option 2. 

### Option 2: Galaxy

Can use the EBI SRA tool in Galaxy (https://usegalaxy.org/) to retrieve the data. 

Note: will have to retrieve 2 files per run (for the SRR1554* experiments, this means file 2 and 3 in the EBI interface).

## Note on data used

Due to limitations in networking and computing power, option 2 will be used for this analysis pipeline. However, the public Galaxy server has a limitation of 250 GB per user, so unfortunately it will not be possible to use all samples. The minimum accepted by the course is 3 adult and 3 fetal samples. 

### Selecting which samples to use

TO-DO: describe here

## Alignment

Human genome version: hg38 (going for the latest release, even though in the paper they used hg19)

Task: align the data with a spliced aligner (some options include Tophat2, Hisat, STAR, but there are others) 

Aligner in Galaxy: HISAT2 (TopHat is marked as deprecated)

## Phenotype

A table with phenotype data can be created from data shown in BioSample: https://www.ncbi.nlm.nih.gov/biosample/?term=R3462_DLPFC_polyA_RNAseq_total


