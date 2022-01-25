# Download Raw Data


## Option 1

> Note: You will need to have conda installed on the TACO cluster for this option.

1. Visit [NCBI's SRA Run Selecter](https://www.ncbi.nlm.nih.gov/Traces/study/)
2. Search the accession number for your study
   - (The accession number for the APEX-Seq data is PRJNA476786)
3. Sign in to the TACO cluster and navigate to your `rawdata` folder from the command line
4. Activate your conda environment using the code
   ```
   conda activate /storage/fazal/software/SRA2.10.0/venv
   ```
5. For each `fastq` file that you want to download, run the code
   ```
   fasterq-dump --split-files SRRXXXXXX
   ```
   (where "SRRXXXXXX" is the "Run" number copied and pasted from NCBI's SRA Run Selecter).


## Option 2
1. Visit [https://sra-explorer.info/](https://sra-explorer.info/)
2. Search the accession number for the experiment files you want to download
   - (The accession number for the APEX-Seq data is PRJNA476786)
3. Select the files you would like to download
4. Click the blue button that says "Add # to collection"
5. Click the blue button with the shopping cart icon that says "# saved datasets"
6. Select the link "Bash script for downloading FastQ files"
7. Press the "Copy" button
8. Sign in to the TACO cluster and navigate to your `rawdata` folder from the command line
9. Paste the code to start your download
   - (The download will go one file at a time, so you will need to press "Enter" after each file 
     finishes downloading) 
     
