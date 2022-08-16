# Download Raw Data


1. Visit [https://sra-explorer.info/](https://sra-explorer.info/).
2. Search for `PRJNA476786` (this is the accession number for the APEX-seq data).
3. Select the files you would like to download (they should be highlighted in green with a blue 
   checkbox once they are selected).
4. Click the blue button at the top of the results that says "Add # to collection".
5. Click the blue button at the top of the page with the shopping cart icon that says "# saved datasets".
6. Select the link "Bash script for downloading FastQ files".
7. Press the "Copy" button.
8. Open your SSH client file viewer (WinSCP or FileZilla) and sign in to the TACO cluster.
9. Create a new file called `download.sh`, paste the copied content into the file, and save.
10. Right click on the file, select "Properties", check all of the Execute (or X) boxes under "Permissions" 
    (this will give the computer permission to run the code), and click "OK".
11. Open your command prompt (Windows) or terminal (Apple) and sign in to the TACO cluster.
12. Make sure you are in the same folder as the file you just created (you should see 
    "download.sh" listed when you run the `ls` command).
13. Run the command `sbatch --time=UNLIMITED download.sh` (it will submit a batch job for the 
    computer to run the code and download your data files).
14. Run the command `squeue --me` (it will show you the status of all the jobs you have submitted).
    The ouput will look something like this:
    ```
     JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
    ######     mhgcp download   userID  R      00:42      1 mhgcp-m00
    ```
    > This example shows that 42 seconds have elapsed since the job started. (Note: Batch jobs don't always start 
    > immediately. Sometimes your job has to wait in the queue for computational resources to become available.)
15. You will know that your download job is finished once you run `squeue --me` and see that your job is no 
    longer listed. Make sure that all of your files are now on the cluster before returning to the 
    [main page](https://fazallabbcm.github.io/FazalLabPipelines/QuickStart) to run the pipelines.
     
