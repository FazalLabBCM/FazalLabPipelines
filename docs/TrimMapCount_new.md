# TrimMapCount

## Setup

If you are not a member of the Fazal Lab and don't have access to Baylor College 
of Medicine's MHGCP cluster, follow this link to [download and setup the pipeline]() 
on your local computing environment.

#### Naming raw data files

Rename your raw FASTQ files so that each file name has these 5 things (in order and separated by underscores):
   1. Subcellular location (can't contain an underscore)
   2. Experimental condition or "none" (can't contain an underscore)
   3. "target" or "control" (first letter can be capitalized)
   4. A number to indicate which target or control sample (one digit 0-9)
   5. "R1.fastq" or "R2.fastq" (or "R1.fastq.gz" and "R2.fastq.gz" for zipped files)


For example, single-end (R1 only) APEX-seq data from the cytosol (where APEX2 enzyme is attached to NES protein) with 
two target samples (treated with puromycin) and two control samples (untreated) might be named like this:
   ```
   Cytosol-NES_puromycin_target_1_R1.fastq
   Cytosol-NES_puromycin_target_2_R1.fastq
   Cytosol-NES_puromycin_control_1_R1.fastq
   Cytosol-NES_puromycin_control_2_R1.fastq
   ```

## Running the Pipeline


## What next?
