# MLS4002NEF 2026 Summer Practical 2
This is the README of MLS4002NEF 2026 Summer Practical 2.

## Objectives
- Familiar with the CLI and basic Linux commands.
- Download FASTQ files from SRA and EMBL-EBI.
- Generate FASTQC report.

## Manual
### Setup
1. Get your codespaces up and running
   1. Clone this repository. Click `Fork` 
   2. Click the upper right corner Green button `<> Code` and then click `Create codespace on main` to open the codespace. Wait a few minutes for the codespace to be ready.
   3. Your virtual computer is ready.
2. Familiar with the CLI.
   1. Check your current directory with `pwd`. Your current directory shall be `/workspaces/mls4002nef-2026`.
   2. List the files in your current directory with `ls`. This show you the files in the current directory.
   3. Create a new directory with `mkdir downloads`.
   4. Check the content of your home directory with `ls` again. You shall see the newly created directory `downloads`.
   5. Change your current directory to `downloads` with `cd downloads`. You shall see the prompt changed to `~/downloads`.
   6. Check your current directory with `pwd`. You shall see `/workspaces/mls4002nef-2026/downloads`.
3. Download the FASTQ data from SRA.
   `fastq-dump`
4. Download the FASTQ data from EBI.
   `wget`
5. Check the file size of the downloaded data with `ls -l`. The fifth column is the file size in bytes. What is the file size of your downloaded data?


### FASTQC
1. Run FASTQC on your downloaded data.
   `fastqc`
2. Download the report into your own laptop by placing your mouse cursor at the left panel `EXPLORER` and then right click `Download..`. It will download the HTML report at your local computer.
3. Find the downloaded HTML report and open it by right clicking the file and select `Open With..` and then select the browser.

### Inspect FASTQ
1. Unzip your downloaded FASTQ file.
2. Inspect the first 10 lines of the FASTQ file.
3. What do you see?

### Clean up
1. Go back to the GitHub repo, click the green button `<> Code` and click `...` and then `Delete`,
   !!! Remember to DELETE the codespace, otherwise you will be charged for the usage of the codes.

## Summary

