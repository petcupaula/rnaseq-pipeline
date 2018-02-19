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

Three samples were selected from each age group, based on the highest RIN values. 

```
Select	Group	Sample name	Experiment	Runs	Age	Source	Sex	Region	Disease	Race RIN Fraction
x	Fetal	R3452_DLPFC_polyA_RNAseq_total	SRX683795	SRR1554537,SRR2071348	-0.3836	LIBD	female	DLPFC	control	AA	9.6	total
	Fetal	R3462_DLPFC_polyA_RNAseq_total	SRX683796	SRR1554538,SRR2071349	-0.4027	LIBD	female	DLPFC	control	AA	6.4	total
	Fetal	R3485_DLPFC_polyA_RNAseq_total	SRX683799	SRR1554541,SRR2071352	-0.3836	LIBD	male	DLPFC	control	AA	5.7	total
x	Fetal	R4706_DLPFC_polyA_RNAseq_total	SRX683824	SRR1554566,SRR2071377	-0.4986	LIBD	male	DLPFC	control	HISP	8.3	total
x	Fetal	R4707_DLPFC_polyA_RNAseq_total	SRX683825	SRR1554567,SRR2071378	-0.4027	LIBD	male	DLPFC	control	AA	8.6	total
	Fetal	R4708_DLPFC_polyA_RNAseq_total	SRX683826	SRR1554568,SRR2071379	-0.4986	LIBD	male	DLPFC	control	AA	8	total
x	Adult	R2869_DLPFC_polyA_RNAseq_total	SRX683793	SRR1554535,SRR2071346	41.58	LIBD	male	DLPFC	control	AA	8.7	total
	Adult	R3098_DLPFC_polyA_RNAseq_total	SRX683794	SRR1554536,SRR2071347	44.17	LIBD	female	DLPFC	control	AA	5.3	total
x	Adult	R3467_DLPFC_polyA_RNAseq_total	SRX683797	SRR1554539,SRR2071350	36.5	LIBD	female	DLPFC	control	AA	9	total
	Adult	R3969_DLPFC_polyA_RNAseq_total	SRX683814	SRR1554556,SRR2071367	36.98	LIBD	male	DLPFC	control	AA	8.5	total
x	Adult	R4166_DLPFC_polyA_RNAseq_total	SRX683819	SRR1554561,SRR2071372	43.88	LIBD	male	DLPFC	control	AA	8.7	total
	Adult	R2857 DLPFC polyA+ transcriptome	SRX683792	SRR1554534,SRR2071345	40.42	LIBD	male	DLPFC	control	AA	8.4	total
```

## Alignment

Human genome version: hg38 (going for the latest release, even though in the paper they used hg19)

Task: align the data with a spliced aligner (some options include Tophat2, Hisat, STAR, but there are others) 

Aligner in Galaxy: HISAT2 (TopHat is marked as deprecated)

## Phenotype

A table with phenotype data can be created from data shown in BioSample: https://www.ncbi.nlm.nih.gov/biosample/?term=R3462_DLPFC_polyA_RNAseq_total


