# BamToBigWig
Generate BigWig files for viewing genome tracks using tools such as the 
[UCSC Genome Browser](https://genome.ucsc.edu/)


## Usage

1. Make sure that `TrimMapCount.sh` has already been run on all of the data that you 
would like to process. For every `fastq` file that was mapped in the project's `rawdata` 
folder, there should be a file ending in "_trim_starAligned_sortedByCoord.out.bam" in the 
project's corresponding `data` folder.

2. From the command line, navigate to the project directory where you would like the Slurm 
`log` file to be generated.

3. Submit a Slurm job  with the code 
   ```
   sbatch /storage/fazal/projects/2022_BamToBigWig/BamToBigWig.sh data
   ``` 
   (where `data` is the absolute path to a directory containing the subdirectories that hold the `bam` 
   files to be processed).
