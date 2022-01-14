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
(for example: YYYYMMDD_MyProject). Your file structure and file names should look something like this:
![](img/fazallab_filestructure.png){width=500px}
Everyone naming and arranging their folders this same way will keep the TACO cluster organized.


## Execution
