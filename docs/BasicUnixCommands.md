# Introduction to Using the Command Line

Welcome! This page will give you a quick introduction to using the TACO cluster. When you 
sign in to the TACO cluster, everything is controlled by the command line, which is where 
you type commands for the computer to execute. Here are a few simple commands.


## Sign in to the TACO cluster
Type this command, replacing `myuserid` with your user ID:
```
ssh myuserid@taco.grid.bcm.edu
```
Then press "Enter".

When prompted, type your password and press "Enter".

Now you're in!


## Navigate

You may be wondering, "Now I'm in? In where? Where am I on the TACO cluster?" That's a great 
question! Here's a map:

<img src="img/youarehere.png" width="40%" height="40%">

You are in a folder named `myuserid`, which is inside a folder named `home`. The folder `home` 
is inside a folder named `fazal`, which is inside the "root" folder named `storage`. To quickly 
describe where you are, this is your address:
```
/storage/fazal/home/myuserid
```
This address is also called an absolute path, because it shows the path to your location all the 
way from the "root" folder. To show your current location on the screen, type the command `pwd` and 
press "Enter". `pwd` stands for "Print Working Directory", which is the same as "show current folder".

<img src="img/pwd.png" width="30%" height="30%">


pwd
cd
ls


## Create, copy, and rename

mkdir
cp
mv
