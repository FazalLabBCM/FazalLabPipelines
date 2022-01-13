# Fazal Lab Pipelines
Congratulations! You have just collected raw data from an experiment, and now you need 
to process it! This page has instructions for when and how to use use each of the 
Fazal Lab pipelines.


## Begin Here
The raw sequencing data you collected is in `fastq` format. It may also be compressed 
or zipped to save space (if so, the file names will end in ".gz"). It isn't very 
useful or even readable the way it is, but it contains the results of your experiment! 
Your goal is to process this raw data with the provided pipelines in order to generate 
useful output files and figures. Follow the steps and links below to begin!

1. To start, use the [TrimMapCount](https://fazallabbcm.github.io/FazalLabPipelines/TrimMapCount) 
   pipeline. This is always step 1. It will map your RNA sequences to a reference genome and count 
   how many reads map to each gene. This process produces useful data files from your raw data.

2. Next, run the [ProcessCounts](https://fazallabbcm.github.io/FazalLabPipelines/ProcessCounts.md) 
   pipeline. This will use the output from TrimMapCount to create simple tables and figures. These 
   tables and figures help show the quality of your raw data and the results of your experiment.

3. Then, use the pipeline [BamToBigWig](https://fazallabbcm.github.io/FazalLabPipelines/BamToBigWig). 
   This pipeline uses the output from TrimMapCount to create BigWig files for your data. BigWig 
   files can be uploaded and viewed in interactive tools such as the [UCSC Genome Browser](https://genome.ucsc.edu/).