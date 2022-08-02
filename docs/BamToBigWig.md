# Data Visualization for RNA-Seq Experiments

The BamToBigWig pipeline is designed to convert BAM files to normalized, 
united, and averaged BigWig files, which can be viewed using interactive tools 
such as the [UCSC Genome Browser](https://genome.ucsc.edu/).


## Setup

If you are not a member of the Fazal Lab and don't have access to Baylor College 
of Medicine's MHGCP cluster, follow this link to 
[download and setup the pipeline](https://fazallabbcm.github.io/BamToBigWig/DownloadAndSetup) 
on your local computing environment.

Make sure you run the [TrimMapCount](https://fazallabbcm.github.io/TrimMapCount) pipeline first.
Once it has finished successfully, you are ready to run the BamToBigWig pipeline.


## Running the Pipeline

1. From the command line, add the BamToBigWig scripts folder to your PATH environment variable. 
   For Fazal Lab members, this can be done with the following code:
   ```
   export PATH=/storage/fazal/pipelines/BamToBigWig/scripts:"${PATH}"
   ```
   
2. Run the following code:
   ```
   BamToBigWig -d /path/to/data
   ```
   > **Note:** Just like ProcessCounts, only run BamToBigWig once. This pipeline creates genome 
   > tracks for every condition in your experiment at the same time. If your aligned data files 
   > are separated into subfolders, just supply the path to the folder containing the subfolders.
3. Make sure that the processed data file path is correct. Then enter "y" to start the pipeline.


## What next?

You can check the log file in your processed data folder to see the progress of your job as it runs.

If you encounter any errors, see our 
[troubleshooting](https://fazallabbcm.github.io/BamToBigWig/Troubleshooting) page for help.

Once BamToBigWig has finished, you are ready to view your experiment's genome tracks. Follow these 
steps to view your genome tracks using the [UCSC Genome Browser](https://genome.ucsc.edu/):

  1. Upload your BigWig files somewhere where they can be accessed on the internet through a public link. 
     (For help deciding where to host your data, visit https://genome.ucsc.edu/goldenpath/help/hgTrackHubHelp.html#Hosting.)
     
     > **Fazal Lab Members:**
     > 1. Sign in to [BackBlaze](https://www.backblaze.com/)
     > 2. Click "Browse Files"
     > 3. Select the bucket "BigWigFiles"
     > 4. Add a new folder for your experiment
     > 5. Open the new folder and upload your BigWig files
  2. Make a custom [track line](https://genome.ucsc.edu/goldenpath/help/hgTracksHelp.html#TRACK) for each of 
     your BigWig Files. Use this example of a track line to get started:
     
     ```
     track type=bigWig name="Sample Name" description="Sample Description" bigDataUrl=https://myhostingservice.com/myBigWigFile.bw color=0,0,0 visibility=full
     ```
     
     > **Fazal Lab Members:**
     > 
     > To get the `bigDataUrl` for your BigWig file, click on the file in BackBlaze to see its details, then 
     > copy the "Friendly URL".
  3. Open the UCSC Genome Browser [custom track management page](https://genome.ucsc.edu/cgi-bin/hgCustom). 
     Paste your custom track lines into the "Paste URLs or data" text box, then press "Submit".
