## Getting Started

- Open a terminal and, using SSH, log in as saanikac@derecho.hpc.ucar.edu
- Change directory to /glade/work/saanikac
- Create a new folder using mkdir eas6995

## Job script

- Create a new training PBS file using vim script.pbs
- Use i to edit the .pbs file
- Write the following code:
```
#!/bin/bash
#PBS -N test                             #Job name
#PBS -l select=1:ncpus=1:mem=4GB         #Resource specification    
#PBS -l walltime=00:30:00
#PBS -j oe                               #Combine any standard output and error
#PBS -A UCOR0090                         #Project Code
#PBS -q main                             #Run on Derecho

module load conda
python script.py
```

- Press esc, save the .pbs file with ":wq".
- Submit the file using qsub script.pbs
- Monitor the submission using qstat -u #USER
- If the status is R, it is running. Once it stops running, qstat returns nothing.
- We can see the output of the script by running vim script.jobnumber where you can get job number from the qsub
- In this script, the output will just say "no file named script.py" because I haven't written a script.py file yet.

## JupyterHub

- Another way to access the .pbs scripts and the python files is using JupyterHub. For that, go to https://jupyterhub.hpc.ucar.edu/ and log in. Use Casper Login node. Go to your work place by going to /tree/work/saanikac/eas6995.
- The test script and output from SSH will also be visible here. You can create a new jupyter notebook over here and save it, write a new .pbs script to run it, and then submit it using SSH.
- To upload a jupyter notebook you've written on your local machine already, use scp /Desktop/test.py saanikac@derecho.hpc.ucar.edu:/glade/work/saanikac/eas6995. RUN IT ON BASE, NOT SSH.

## Monitoring System Usage

- To keep tabs on your core hours usage and active jobs go to sam.ucar.edu
