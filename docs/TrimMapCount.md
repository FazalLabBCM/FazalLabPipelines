# TrimMapCount
The [TrimMapCount](https://fazallabbcm.github.io/FazalLabPipelines/TrimMapCount) pipeline will map 
your RNA sequences to a reference genome and count how many reads map to each gene. This process 
produces useful data files from your raw data.


## Setup

On the TACO cluster, the Fazal lab has folders named `rawdata`, `data`, and `projects`. The 
`rawdata` folder is for your raw data files, the `data` folder is for your processed data files, 
and the `projects` folder is for all of your tables, figures, and log files (log files keep track 
of the progress of your running projects).

To use the pipelines, you will need to know how to use a few simple commands on the TACO cluster. 
I you don't know how to sign in to the cluster, navigate in and out of folders, or make new folders, 
visit this link: [Basic Linux Commands](https://fazallabbcm.github.io/FazalLabPipelines/BasicLinuxCommands)

To begin, you should create a `rawdata` folder, `data` folder, and `project` folder all with the 
same name. The name should have today's date and a title for your project separated by an underscore 
(for example: `YYYYMMDD_MyProject`). Your file structure and file names should look something like this:

<img src="img/fazallab_filestructure.png" width="50%" height="50%">

Everyone naming and arranging their folders this same way will help keep the TACO cluster organized.

Next, make sure there is a folder named `star` inside `/storage/fazal/genome/human/2021` and that it 
is not empty. This folder is important for your data to align to the genome. It likely already 
exists and has files in it, but visit [this page](https://fazallabbcm.github.io/FazalLabPipelines/GenerateGenome) 
if not.

Finally, make sure that each of your `fastq` files are named following these rules:
   * Each file name has the word "Target" or "Control", surrounded by underscores
   * Each file name has the abbreviation (in all caps) for the sample location, surrounded by underscores
   * Each file name contains which number of target or control, surrounded by underscores
   * Each file name ends in "R1.fastq" or "R2.fastq" (or "R1.fastq.gz" and "R2.fastq.gz")
   * For example, data from the nucleus with two target samples and one control sample might be named like this:
   ```
   Nucleus_NLS_Target_1_R1.fastq
   Nucleus_NLS_Target_1_R2.fastq
   Nucleus_NLS_Target_2_R1.fastq
   Nucleus_NLS_Target_2_R2.fastq
   Nucleus_NLS_Control_1_R1.fastq
   Nucleus_NLS_Control_1_R2.fastq
   ```
   More information can be added to the file names if desired.



## Execution

From the command line, navigate to the project directory where you would like the Slurm `log` file 
to be generated.

Submit a Slurm job  with the code 
```
sbatch /storage/fazal/projects/2022_TrimMapCount/TrimMapCount.sh rawdata data
``` 
(where `rawdata` is the absolute path to a directory containing the `fastq` files to be used for 
alignment, and `data` is the absolute path to a directory where the output files will be generated).

