# Check Genome Build of ChIP-seq Aligned Files

This is a simple snakemake-based pipeline used in the Zwart lab at the Netherlands Cancer Intitute to check the genome build 
of ChIP-sequencing experiments. A correctly aligned file (from previous experiments) is used as a comparison to check the 
alignment information using the header of the newly aligned files.

The pipeline performs the following steps to produce a final text file:
  - Download the correct header information and sort it.
  - Create sorted header information files from the newly aligned *.mq20.bam files
  - For each *.mq20.bam file, paste the header information from that file next to the correct header file information
  
 ## Installation and use  ##
 The pipepline is designed to be used after peak-calling has been run using Yongsoo's snakemake-based method.
 (https://github.com/anoyaro84/snakemake_ChIPseq/). In the folder where you ran your peak-calling check that there is a 'bams' 
 folder and a 'qc' folder. The pipeline relies on the folder configuration from the peak-calling so don't move anything until
 you have finished with the Genome Build Check.
 
 Navigate to the 'qc' folder and download the repository:
 
 ```bash
 git clone https://github.com/tesa1/gbuild_check
 ```
 
 The file needed for comparison will be downloaded along with the repository.
 
 ```bash
 snakemake -s gbuild_check
 ```
 
