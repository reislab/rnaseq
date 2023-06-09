# Nextflow RNA-seq pipeline for UBELIX
Implementation of nf-core/rnaseq to UBELIX (UniBE's HPC cluster).

- nextflow 22.10.1
- nf-rnaseq 3.11.1

## Set-up GitHub repo 

1. Make your repo public **before** cloning it.
2. Set-up git for repo cloning in UBELIX

Create a Personal Access Token (PAT) in GitHub
In GitHub, go to:
> Settings > Developer settings > Personal access tokens

Create a PAT without expiration date, but with limited read-only access by enabling:
- repo:status
- public_repo
- read:packages
- read:public_key
- read:ssh_signing_key

**SAVE YOUR PAT IN A SECURE PLACE.**

## Clone repo in UBELIX
Go to your UBELIX workspace

``
cd /storage/workspaces/ips_reislab/reislab/"your-surname"
``

Then, clone repo:

``
git clone https://github.com/reislab/rnaseq.git
``

- username: GitHub username
- password: PAT created above

## Run script
Go to directory with script and run: 

``
sbatch your-script.sh
``

## Copy results to local directory
In the local terminal, run (replace "user" and "your-surname"):

``
scp -r "user"@submit03.unibe.ch:/storage/workspaces/ips_reislab/reislab/"your-surname"/nf-rnaseq-ubelix/results /path/to/target_dir/
``

## Troubleshooting Nextflow
Copy nextflow.log file (not in the results directory above):

``
scp -r "user"@submit03.unibe.ch:/storage/workspaces/ips_reislab/reislab/"your-surname"/nf-rnaseq-ubelix/.nextflow.log /path/to/target_dir/
``

> How to run a nf pipeline (https://nf-co.re/docs/usage/introduction#how-to-run-a-pipeline)

> Troubleshooting nf pipeline (https://nf-co.re/docs/usage/troubleshooting).

## How to delete a repo directory (local or cluster)
Repo directory creates write-protected files that will ask you for confirmation if you use ``rm -r``. Instead, use ``rm -rf`` where the -f argument forces the ``rm`` to delete files without asking for confirmation. **Careful when using it!**



scp -r rs21h732@submit03.unibe.ch:/storage/workspaces/ips_reislab/reislab/reis/nf-rnaseq-ubelix/results ~/Dropbox/reislab/00-projects/reislab/github/nf-rnaseq-ubelix

scp -r rs21h732@submit03.unibe.ch:/storage/workspaces/ips_reislab/reislab/reis/nf-rnaseq-ubelix/.nextflow.log ~/Dropbox/reislab/00-projects/reislab/github/nf-rnaseq-ubelix
