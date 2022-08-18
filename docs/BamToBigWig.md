# BamToBigWig: Data Visualization for RNA-Seq Experiments

The BamToBigWig pipeline uses the output from 
[TrimMapCount](https://fazallabbcm.github.io/FazalLabPipelines/TrimMapCount) to create genome tracks for your 
data. The genome tracks will be stored in BigWig files that can be uploaded and viewed in interactive tools 
such as the [UCSC Genome Browser](https://genome.ucsc.edu/).


## Setup

Make sure you run the [TrimMapCount](https://fazallabbcm.github.io/FazalLabPipelines/TrimMapCount) pipeline first.
Once it has finished successfully, you are ready to run the BamToBigWig pipeline.


## Running the Pipeline

1. Copy and paste this code in the command line and press “Enter”. (It will tell the computer where to 
   find the code for the pipeline.)
   
   ```
   export PATH=/storage/fazal/pipelines/BamToBigWig/scripts:"${PATH}"
   ```
   
2. Run the following code (replacing the file path with the path to your experiment’s processed 
   data folder):
   
   ```
   BamToBigWig -d /storage/fazal/data/yourname/yourexperiment
   ```
   
   > **Note:** Just like ProcessCounts, only run BamToBigWig once. This pipeline creates genome 
   > tracks for every condition in your experiment at the same time. If your aligned data files 
   > are separated into subfolders, just supply the path to the folder containing the subfolders.

3. Make sure that the processed data file path is correct. Then enter "y" to start the pipeline.


## What next?

You can check the “BamToBigWig.log” file in your processed data folder to see the progress of your job as it 
runs. It will say “DONE” at the bottom of the log file when the pipeline has finished successfully.

Once BamToBigWig has finished, follow this tutorial to view your genome tracks: 
[Viewing Genome Tracks in the UCSC Genome Browser](https://fazallabbcm.github.io/FazalLabPipelines/CreateGenomeBrowserSession)
