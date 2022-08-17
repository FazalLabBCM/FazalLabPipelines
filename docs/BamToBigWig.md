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

Once BamToBigWig has finished, you are ready to view your experiment's genome tracks. Follow these 
steps to view your genome tracks using the [UCSC Genome Browser](https://genome.ucsc.edu/):

#### Host BigWig Files Online
  1. Go to your processed data folder on the cluster and download every BigWig file that ends in 
     "controls_uns.norm_avg.bw" or "targets_uns.norm_avg.bw" to your local computer.
     > **Note:** If you chose to combine controls for data analysis with ProcessCounts, only download one 
     > control file: "all_controls_uns.norm_avg.bw"
     
     > **Note:** "uns" stands for unstranded. If you would like to see separate genome tracks 
     > for the forward and reverse strands, download the files ending in "controls_fwd.norm_avg.bw", 
     > "controls_rev.norm_avg.bw", "targets_fwd.norm_avg.bw", and "targets_rev.norm_avg.bw" instead.
  2. Sign in to [BackBlaze](https://www.backblaze.com/) (this is the online data hosting service we use in the lab). 
     > **Note:** The sign in information is in the Lab Passwords document on OneDrive.
  3. Click "Browse Files", then select the bucket "BigWigFiles".
  4. Add a new folder for your experiment.
  5. Open the new folder and upload your BigWig files.
#### Add Tracks to the Genome Browser
  6. Open Notepad (Windows) or TextEdit (Mac).
  7. For each BigWig file that you uploaded to BackBlaze: copy and paste this track line on a new line in the blank 
     note, then replace `Name` and `URL`.
     ```
     track type=bigWig name="Name" bigDataUrl=URL visibility=hide
     ```
     > **Note:** The `Name` of your track is the name of your BigWig file (but you can remove ".norm_avg.bw" and use 
     > spaces instead of underscores if you want).
     
     > **Note:** To get the `URL` for your BigWig file, click on the file name in BackBlaze to see its details, 
     > then copy the "Friendly URL".
  8. [Login to the UCSC Genome Browser](https://genome.ucsc.edu/cgi-bin/hgLogin?hgLogin.do.displayLoginPage=1) 
     (or sign up if you don't have an account).
  9. Open the [custom track management page](https://genome.ucsc.edu/cgi-bin/hgCustom) to add your custom tracks.
  10. Paste your custom track lines into the "Paste URLs or data" text box, then press "Submit".
#### Create Track Collection
  11. "My Data" "Track Collection Builder"
  12. "Add Collection"
  13. "Custom Tracks" and click plus sign
  14. change color of targets
  15. "Go"
#### Save Session
  16. "Configure" screen
  17. GENCODE genes
  18. any other edits to tracks
  19. "My Data" "My Sessions"
  20. Under "Save Settings" change name and click "submit"
