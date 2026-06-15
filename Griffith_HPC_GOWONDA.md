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

## Working with conda env in PBS job

### Method 1:
```bash
cd $PBS_O_WORKDIR 
module load anaconda3/2024.06
conda run -n r_env Rscript
```
 
### Method 2:
```bash
module load anaconda3/2024.06
source /sw/anaconda3/2024.06/etc/profile.d/conda.sh
conda activate r_env
Rscript my_script.R
```
### Method 3: Recommended
```bash
source ~/.bashrc
conda activate r_env
```
