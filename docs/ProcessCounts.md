# ProcessCounts
The [ProcessCounts](https://fazallabbcm.github.io/FazalLabPipelines/ProcessCounts) pipeline 
will use the output from [TrimMapCount](https://fazallabbcm.github.io/FazalLabPipelines/TrimMapCount) 
to create simple tables and figures. These tables and figures help show the quality of your 
raw data and the results of your experiment.


## Setup


## Execution



## Usage

1. Make sure that `TrimMapCount.sh` has already been run on all of the data that you 
would like to process. For every `fastq` file that was mapped in the project's `rawdata` 
folder, there should be a file ending in "_aligned.txt" and a file ending in 
"_trim_starLog.final.out" in the project's corresponding `data` folder.

2. From the command line, navigate to the project directory where you would like the Slurm 
`log` file and figures to be generated.

3. Submit a Slurm job  with the code 
   ```
   sbatch /storage/fazal/projects/2022_ProcessCounts/ProcessCounts.sh data prefix
   ``` 
   (where `data` is the absolute path to a directory containing the subdirectories that hold the `txt` 
   and `out` files to be processed, and `prefix` is the file prefix to be used for all of the project's 
   output files).
