# Griffith Gowonda HPC
First we should get the access to Griffith HPC
## To login 
```bash
ssh -y snumber@clogin1.rcs.griffith.edu.au
```

## To load Anaconda
```bash
module load anaconda3/2024.06
conda config --add channels defaults
conda config --add channels bioconda
conda config --add channels conda-forge
```

## Once we have conda module loaded we can create an R env using conda

```bash
conda create -n r_env r-base r-essentials -y
```

## Issue with internet connection
Sometime there won't be internet access in the login node, at that time we can change the node to n059 using:

```bash
ssh n059
```
## OR source the proxy file

```bash
source /usr/local/bin/s3proxy.sh
```

