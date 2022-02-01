# BamToBigWig
The [BamToBigWig](https://fazallabbcm.github.io/FazalLabPipelines/BamToBigWig) pipeline uses the 
output from [TrimMapCount](https://fazallabbcm.github.io/FazalLabPipelines/TrimMapCount) to create 
genome tracks for your data. The genome tracks will be stored in `bw` files that can be uploaded and 
viewed in interactive tools such as the [UCSC Genome Browser](https://genome.ucsc.edu/).



## Setup

Make sure that you have already run the 
[TrimMapCount](https://fazallabbcm.github.io/FazalLabPipelines/TrimMapCount) pipeline on all of your 
raw data. If this has already been done, then, for every `fastq` file in your project’s rawdata 
folder, there should be a file ending in “_trim_starAligned_sortedByCoord.out.bam” in your project’s 
corresponding data folder. These `bam` files will be used to generate the genome tracks.



# Execution

1. From the command line, navigate to your `project` folder. This is where the log file will be generated, which 
   will keep track of your project's progress as the pipeline runs.
   - (In the example, the absolute path would be `/storage/fazal/projects/yourname/20220101_SequencingData`.)

2. Copy and paste the code
   ```
   sbatch /storage/fazal/projects/3_BamToBigWig/BamToBigWig.sh data
   ```
   in the command line.

3. Replace `data` with the absolute path to your project's `data` folder.
   - (In the example, the absolute path would be `/storage/fazal/data/yourname/20220101_SequencingData`.)

4. Press "Enter" to start the pipeline.
