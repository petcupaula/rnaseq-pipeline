# rnaseq-pipeline

## Setup

### Download the files

Download SRA Toolkit: https://trace.ncbi.nlm.nih.gov/Traces/sra/sra.cgi?view=software

Unarchive and configure (change workspace directory as described here: https://trace.ncbi.nlm.nih.gov/Traces/sra/sra.cgi?view=toolkit_doc&f=std):

```
cd bin
./vdb-config -i
```

```
./fastq-dump -v --gzip SRR1554537
```

### Alignment

Human genome version: ? (in the paper they used hg19)

TO-DO: align the data with a spliced aligner (some options include Tophat2, Hisat, STAR, but there are others) 

### Phenotype

Can be created from data shown in BioSample: https://www.ncbi.nlm.nih.gov/biosample/?term=R3462_DLPFC_polyA_RNAseq_total


