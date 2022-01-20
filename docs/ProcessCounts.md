# ProcessCounts
The [ProcessCounts](https://fazallabbcm.github.io/FazalLabPipelines/ProcessCounts) pipeline 
will use the output from [TrimMapCount](https://fazallabbcm.github.io/FazalLabPipelines/TrimMapCount) 
to create simple tables and figures. These tables and figures help show the quality of your 
raw data and the results of your experiment.



## Setup


Make sure that you have already run the [TrimMapCount](https://fazallabbcm.github.io/FazalLabPipelines/TrimMapCount) 
pipeline on all of your raw data. If this has already been done, then, for every `fastq` file 
in your project's `rawdata` folder, there should be a file ending in "_aligned.txt" and a file 
ending in "_trim_starLog.final.out" in your project's corresponding `data` folder. These two 
types of output files will be used to generate tables and figures.



## Execution


1. From the command line, navigate to your `project` folder.
   - (In the example, the absolute path would be `/storage/fazal/projects/yourname/20220101_SequencingData`.)

2. Copy and paste the code
   ```
   sbatch /storage/fazal/projects/2_ProcessCounts/ProcessCounts.sh data ProjectName
   ```
   in the command line.

3. Replace `data` with the absolute path to your project's `data` folder.
   - (In the example, the absolute path would be `/storage/fazal/data/yourname/20220101_SequencingData`.)

4. Replace `ProjectName` with a name for your project (preferably the same name that you chose for your 
   project folders). This name will be added to the file name for each of your project's output files.
   - (In the example, the `ProjectName` would be "SequencingData".)

5. Press "Enter" to start the pipeline.

