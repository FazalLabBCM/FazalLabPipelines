# ProcessCounts: Data Analysis for RNA-Seq Experiments

The ProcessCounts pipeline will use the output from 
[TrimMapCount](https://fazallabbcm.github.io/FazalLabPipelines/TrimMapCount) to create simple tables 
and figures. These tables and figures help show the quality of your raw data and the results of your 
experiment.


## Setup

Make sure you run the [TrimMapCount](https://fazallabbcm.github.io/TrimMapCount) pipeline first.
Once it has finished successfully, you are ready to run the ProcessCounts pipeline.


## Running the Pipeline

1. Copy and paste this code in the command line and press "Enter". (It will tell the computer where to find 
   the code for the pipeline.)
   
   ```
   export PATH=/storage/fazal/pipelines/ProcessCounts/scripts:"${PATH}"
   ```
   
2. Run the following code (replacing the file paths with the paths to your experiment's 
   processed data and output folders):
   
   ```
   ProcessCounts -d /storage/fazal/data/yourname/yourexperiment \
                 -o /storage/fazal/projects/yourname/yourexperiment \
                 -n ProjectName
   ```
   
   > **Note:** If your control samples for each experimental condition are the same, add the `-c` option like 
   > this (it will combine the controls for improved analysis and figures):
   > ```
   > ProcessCounts -d /storage/fazal/data/yourname/yourexperiment \
   >               -o /storage/fazal/projects/yourname/yourexperiment \
   >               -n ProjectName \
   >               -c
   > ```

   > **Note:** Only run ProcessCounts once. This pipeline analyzes the data from every condition 
   > in your experiment at the same time. If your aligned data files are separated into subfolders, 
   > just supply the path to the folder containing the subfolders.

   > **Note:** Run `ProcessCounts -h` or `ProcessCounts --help` if you want to see the help menu.
   
3. Make sure that the processed data and output file paths are correct. Then enter "y" to 
   start the pipeline.


## What next?

You can check the "ProcessCounts.log" file in your output folder to see the progress of your job as 
it runs. It will say "DONE" at the bottom of the log file when the pipeline has finished successfully.

Once ProcessCounts has finished, go to your output folder and open the Analysis Summary HTML file in your 
browser (the file is named like "YYYYMMDD_ProjectName_AnalysisSummary.html"). Look for the following things:

  1. Percentage of reads mapped uniquely is greater than 75% for each sample (remove any 
     samples that do not meet this criterion from future analyses) 

  2. Correlation between sample replicates is greater than 0.75 for the best correlated 
     replicates of each condition (repeat the experiment if the two best correlated replicates 
     for any condition have a correlation coefficient less than 0.7) 

  3. Examine the other plots, looking for correlation between replicates as well as differences 
     between experimental conditions

Finally, if you haven't viewed the genome tracks for your experiment yet, use the 
[BamToBigWig](https://fazallabbcm.github.io/FazalLabPipelines/BamToBigWig) pipeline to visualize your data.
