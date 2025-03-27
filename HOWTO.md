## Getting Started

Open a terminal and, using SSH, log in as saanikac@derecho.hpc.ucar.edu

## Job script

- Create a new training PBS file using vim script.pbs
- Use i to edit the .pbs file
- Write the following code:
'''
#!/bin/bash
#PBS -N test
#PBS -l select=1:ncpus=1:mem=4GB
#PBS -l walltime=00:30:00
#PBS -j oe
#PBS -A UCOR0090
#PBS -q main

module load conda
python script.py
'''

- Press esc, save the .pbs file with ":wq".
- Submit the file using qsub script.pbs
- Monitor the submission using qstat -u #USER
- If the status is R, it is running. Once it stops running, qstat returns nothing.
- We can see the output of the script by running vim script.jobnumber where job number needs to be entered

## JupyterLab


