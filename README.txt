# How does salt influence microbial comuunities?
Questions: 
1. How is microbial biodiversity modified across a salinity gradient? 
    	-Null hypothesis: Microbial biodiversity (eg richness) does not vary across a salinity gradient.
	-hypothesis: Microbial richness will increase as salt concentration lowers.
		- There is an inverse relationship between richness and salinity.
2. How does microbial composition change a cross a salinity gradient?  
	-Null hypothesis: Microbial composition does not change across a salinity gradient.
	-Hypothesis: Dominant members of the microbial community are unique in freshwater compared to salt water.
#fastqc and multiqc loading

#LOAD FASTQC
#FULL path: /programs/FASTQC-0.12.1/fastqc
#export PATH=/programs/FastQC-0.12.1:$PATH

## LOAD MULTI QC
export PYTHONPATH=/programs/multiqc-1.15/lib64/python3.9/site-packages:/programs/multiqc-1.15/lib/python3.9/site-packages
export PATH=/programs/multiqc-1.15/bin:$PATH


#code to execute fastqc

fastqc /workdir/rc969/SalinityGradient_16s/data/01_DADA2/01_raw_gzipped_fastqs/*.fastq.gz     --threads 5     -o /workdir/rc969/SalinityGradient_16s/analysis/00_FastQC/fastqc_reports/

#multiqc
multiqc fastqc_reports/ -o multiqc_results/
