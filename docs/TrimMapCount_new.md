# TrimMapCount


## Setup

If you are not a member of the Fazal Lab and don't have access to Baylor College 
of Medicine's MHGCP cluster, follow this link to [download and setup the pipeline]() 
on your local computing environment.


#### Naming raw data files

Rename your raw FASTQ files so that each file name has these 5 things (in order and separated 
by underscores):
   1. Subcellular location (can't contain an underscore)
      * Where APEX is targeted and/or which protein the enzyme is fused to
      * Example: "Cytosol-NES"
   2. Experimental condition or "none" (can't contain an underscore)
      * Could be a time limit, cell type, antibiotic treatment, etc.
      * Example: "puromycin"
   3. "target" or "control" (first letter can be capitalized)
      * Whether H<sub>2</sub>O<sub>2</sub> was added (target) or not (control)
   4. A number to indicate which target or control sample (one digit 0-9)
   5. "R1.fastq" or "R2.fastq" (or "R1.fastq.gz" and "R2.fastq.gz" for zipped files)


For example, single-end (R1 only) APEX-seq data targeting the cytosol (where APEX enzyme is 
attached to NES protein) and treated with puromycin might be named like this:
   ```
   Cytosol-NES_puromycin_target_1_R1.fastq
   Cytosol-NES_puromycin_target_2_R1.fastq
   Cytosol-NES_puromycin_control_1_R1.fastq
   Cytosol-NES_puromycin_control_2_R1.fastq
   ```


#### Sorting raw data files

To save lots of time, separate your FASTQ files into subfolders for each unique combination 
of subcellular location and experimental condition (like the picture below). Then, run the 
TrimMapCount pipeline for each subfolder at the same time.

<img src="img/FileStructureExample.png" width="60%" height="60%">


## Running the Pipeline

1. From the command line, add the TrimMapCount scripts folder to your PATH environment variable. 
   For Fazal Lab members, this can be done with the following code:
   ```
   export PATH=/storage/fazal/pipelines/TrimMapCount/scripts:"${PATH}"
   ```
   
2. Repeat steps 3 and 4 for each subfolder in your experiment's raw data folder.
   
3. Run the following code (replacing the file paths with the correct paths for your experiment's 
   raw data and processed data subfolders):
   ```
   TrimMapCount -r /path/to/rawdata -d /path/to/data
   ```

4. Make sure that the raw data and processed data file paths are correct. Then enter "y" to 
   start the pipeline.


## What next?

You can check the log file in your processed data folder to see the progress of your job as it runs.

Once [TrimMapCount](https://fazallabbcm.github.io/FazalLabPipelines/TrimMapCount) has finished, 
you will have all of the data files necessary for the 
[ProcessCounts](https://fazallabbcm.github.io/FazalLabPipelines/ProcessCounts) and 
[BamToBigWig](https://fazallabbcm.github.io/FazalLabPipelines/BamToBigWig) pipelines.
