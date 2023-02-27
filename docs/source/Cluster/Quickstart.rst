Cluster quick start
===================
This section is a quick start for someone who is somewhat familiar with Linux/Unix and is looking at how to start using the Institut Pasteur de Tunis cluster quickly.

If you're not familiar with omics HPC and Linux in general, many beginner tutorials are available online. Omics Hpc team is also actively working on providing a better guides.

Request an account
==================
In order to open an account with omics HPC, please fill out the form here  to ensure that Omics Hpc team receives all the necessary information to quickly create the account.
https://docs.google.com/forms/d/1vbxurYlNwtrc38sLssLJ865CQf2Awr3kSEAOzl_zjoY/edit

Alternatively you can email your request to dhamer1995@gmail.com . If you've already got a pasteur account, please provide your username with the email. If you are a student, you must also CC your supervisor in the email.


Cluster login¶
==============
You can access Omics HPC cluster from anywhere, but for security reasons please use either of the following:

Be physically in a university building.
Connect from a remote location utilizing omics VPN .
To connect from a Unix-like system like Linux, macOS, WSL, use a Secure Shell Protocol called SSH to log in to 192.168.100.211 with your pasteur credentials:


ssh <username>@192.168.100.211
To connect from a Windows system, please follow guide for PuTTY  or use Windows Subsystem for Linux (WSL). WSL is highly recommended.

Your home directory¶
=====================
The home directory, which makes all files and directories available on all cluster nodes, resides on a shared file system.

Quotas manage the Disk space consumption. There are two types of quotas - user qutoes  and projects quotes. By default, a user has 1 TB of $HOME space.

Tip

Please keep your home directory clean by regularly cleaning old data.



Copy data¶
=====================
There are multiple ways to transfer files between a local machine and the cluster, mainly depending on your local operating system. For a Unix-like OS, you can use scp, rsync, sftp commands on the command line. If you are on Windows or prefer a Graphical User Interface, FileZilla  is one of a tools that you can use.

Info
-----
 

To copy data to the cluster from your local machine, use the secure copy command scp:


scp /path/to/file <username>@@192.168.100.211:/path/to/target_dir/
To retrieve data from the cluster to your local machine:


scp <username>@192.168.100.211:/path/to/file /path/to/target_dir/

Using software¶
================

You can make use of already pre-installed software, or you can compile and install software on your own. Omics Hpc uses an environment module system to make software and specific versions available to users:

For example on searching and loading ’python’ software.

Check the available ’python’ versions on cluster:


module av python
Load the desired version of ’python’:


module load python/3.8.6
List loaded modules:


module list
Warning

Loaded software is only for operating in the current terminal session. If you open a new session, it's a blank slate. Therefore, it's advisable to specify and load the needed modules in your job script.

 

First job¶
==========
The cluster utilizes a scheduler called Slurm to control job execution and distribute running jobs across available physical resources like memory and CPU cores.

The following is an example of how to run your first job. A job script (sbatch file) consists of two main parts - instructions for the scheduler and the actual commands to run for the job, which operate your choice of software. Start with the scheduler instructions:




#!/bin/bash

#SBATCH --time=01:00:00

#SBATCH --job-name="A long job"

#SBATCH --mem=10GB      #the amount of memory 

#SBATCH --output=long-job.out #the output file

#SBATCH --cpus-per-task=1

# your code goes below

Then add the part for loading software and running a command:


module load python/3.8.6

python -c 'print ("Hello world!")'

The finalized job script looks like this and you should save it into a file, for example hello_world.sh:

Submit your job
===============
Once you have a job definition script, you can submit your job script to the scheduler. Scheduler allocates the requested resources for your job and give you a job id. If the requested resources are available, your job start immediately. Otherwise, the job stays in queue until sufficient resources are available. To submit your job to Slurm, use the sbatch command:


sbatch hello_world.sh

Submitted batch job 15304092
If the job submission was successful, the command provides you with a job-ID, which you can refer to later.
Warning

Running jobs directly on the cluster, without the queue system, is strictly forbidden and the jobs are killed!

There are various options for different kinds of jobs in cluster. Please review the following sections for more information Submitting Jobs , GPU Computing , Interactive Jobs  for more information.

Monitor your job
================
You can inspect the status of your running jobs with the squeue command:


squeue -j 15304092

JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
15304092   testing hello_wo    test_user  R       0:10      1 stage43
Here you can see the job ’hello_world’ with job-ID ’15304092’ is in state ’RUNNING’ (R). The job runs on the ’testing’ partition on the node ’stage43’ for 10 seconds.
Be aware, that if the requested resources aren't available, the job status is ’PENDING’ (PD). The job is in the queue, and starts as soon as the requested resources are available.

You can also see all active submitted jobs with squeue:


squeue -u <test_user>

Cancel your job
===============

You can cancel your job via the scancel command by passing the job ID as an argument.


scancel 15304092
