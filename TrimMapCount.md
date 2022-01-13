# TrimMapCount
The [TrimMapCount](https://fazallabbcm.github.io/TrimMapCount) pipeline will map your RNA 
sequences to a reference genome and count how many reads map to each gene. This process produces 
useful data files from your raw data.


## Setup

1. Make sure there is a directory named `star` inside `/storage/fazal/genome/human/2021` and 
that it is not empty. (If this is not true, then first submit a Slurm job with the script 
`GenerateGenome.sh`. After that job has finished, you can move to step 2.)

2. Make sure that each of the `fastq` files to be mapped adhere to the following naming 
conventions:
   * There is the string `_Target_` or `_Control_` in the filename (the first letter can be capital 
   or lowercase)
   * There is the string `_ABBREV_` in the filename (where "ABBREV" is the abbreviation for the 
   sample location in all caps, such as "NLS" for nucleus)
   * The filename contains which number of target or control, surrounded by underscores
   * The filename ends in "R1.fastq" or "R2.fastq" (or "R1.fastq.gz" and "R2.fastq.gz" for gzipped 
   files)
   * For example, data from the nucleus with two target samples and one control sample might be named 
   like this:
   ```
   Nucleus_NLS_Target_1_R1.fastq
   Nucleus_NLS_Target_1_R2.fastq
   Nucleus_NLS_Target_2_R1.fastq
   Nucleus_NLS_Target_2_R2.fastq
   Nucleus_NLS_Control_1_R1.fastq
   Nucleus_NLS_Control_1_R2.fastq
   ```
   More information can be added to the filenames if desired.


## Execution

3. From the command line, navigate to the project directory where you would like the Slurm `log` file 
to be generated.

4. Submit a Slurm job  with the code 
   ```
   sbatch /storage/fazal/projects/2022_TrimMapCount/TrimMapCount.sh rawdata data
   ``` 
   (where `rawdata` is the absolute path to a directory containing the `fastq` files to be used for 
   alignment, and `data` is the absolute path to a directory where the output files will be generated).


Note: Each `fastq` file will take about 2 hours to align, so it is recommended that you divide 
your data into sub-directories containing no more than 12 `fastq` files each. Then, submit a 
Slurm job for each sub-directory of data. (Running jobs in parallel like this will also save 
time.)

