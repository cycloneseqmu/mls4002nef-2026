# MLS4002NEF 2026 Summer Practical 3
This is the README of MLS4002NEF 2026 Summer Practical 3.
> [!NOTE]
> README is a plain-text documentation file that introduces a project, explaining its purpose, how to use it, and other key details. Think of it as a quick reference manual of a kit or an equipment.

## Overview
The practical sessions are designed to get yourself familiar with programmatic access to biological database and sequence analysis, which shall support modern medical laboratory work.

## Objectives
- Familiar with the CLI and basic Linux commands.
- Download FASTQ files from SRA.
- Generate FASTQC and MultiQC report.
- Interpret and understand the FASTQC report.

## Manual
### Linux Commands Cheatsheet
| command | usage |
| ------- | ----- |
| `pwd` | show the **P**resent **W**orking **D**irectory. |
| `cd`  | **C**hange **D**irectory. |
| `ls`  | **L**i**S**t out the contents (both files and directories) inside the current location.  |
| `mkdir` | **M**a**K**e a new **DIR**ectory. |
| `gzip` | Compress file with gzip. |

> [!NOTE]
> Everything is considered as file in Linux. Directory is a special type of file that contains references to other files and directories, organizing them in a hierarchical structure. You can think of a directory is a folder. The top-level directory is called the root directory, denoted by a forward slash (`/`), and all other directories branch off from it.


### Datasets
Refer to [MLS 4002NEF_NGS workshop_Practical 3 Info sheet](https://docs.google.com/spreadsheets/d/10m_xEVQxQHw-Ygqv3WUZ91dNNXBDpw0ETEpL1riOlrQ/edit?usp=sharing).


### Stage 1 - Setup and get started
1. Get your codespaces up and running.
   1. Click the upper right corner Green button `<> Code` and then click `Create codespace on main` to open the codespace. Wait a few minutes (up to 5-10 minutes) for the codespace to be ready.
   2. Your virtual computer is ready.
2. Familiar with the CLI.
   1. Check your current directory with `pwd`. Your current directory shall be `/workspaces/mls4002nef-2026`.
   2. List the files in your current directory with `ls`. This show you the files in the current directory.
      > Try `ls -h`, `ls -a`, `ls -l`. Have you noticed any difference in the output?
   3. Create a new directory with `mkdir downloads`.
   4. Check the content of your home directory with `ls` again. You shall see the newly created directory `downloads`.
   5. Change your current directory to the newly created `downloads` with `cd ./downloads`.
   6. Check your current directory with `pwd` to confirm you're at the correct directory. You shall see `/workspaces/mls4002nef-2026/downloads`.

### Stage 2 - Get to know your tools
1. Explore the help manual of FASTQC and MultiQC with the option `--help` (i.e., `fastqc --help` or `fastqc -h`).
2. What is the difference between FASTQC and MultiQC?
3. Find out the version of your FASTQC, MultiQC based on the help manual.

> [!TIP]
> `-h` is a commmon shorthand of `--help` option, `${COMMAND} -h` will display a brief usage summary and a list of available options for that command.

> [!NOTE]
> Most (but NOT ALL) commands support `-v` option (shorthand of `--version`) to display the version of the tools.


### Stage 3 - Download FASTQ
1. Obtain the accession number from the info sheet.
2. Check the accession with `vdb-dump --info ${ACCESSION}`.
   > What is the size of the accession in bytes?
3. Download the first 1M reads of FASTQ data from SRA using the command `fastq-dump -X 1000000 --split-files ${ACCESSION}`. This can takes a few minutes.
4. Check the file size of the downloaded data with `ls -l`. The fifth column is the file size in bytes.
   > What is the file size of your downloaded data in bytes, Megabyte (MB) and Gigabyte (GB)?
   > 1024B=1MB; 1024MB=1GB
   > Does it match the output above?
5. Compress the fastq with gzip `gzip *.fastq`.
6. Check if the fastq been gzipped with `ls`.

> [!TIP]
> You may get more description of an accession at [NCBI SRA](https://www.ncbi.nlm.nih.gov/sra).


### Stage 4 - FASTQC
1. Run FASTQC on your downloaded data. `fastqc *.fastq.gz`
2. Download the FASTQC and MultiQC report into your own laptop by placing your mouse cursor at the left panel `EXPLORER` and then right click `Download..`. It will download the HTML report at your local computer.
3. Find the downloaded HTML report and open it by right clicking the file and select `Open With..` and then select the web browser (e.g., Safari, Firefox, Chrome, Edge).


### Stage 5 - Inspect FASTQ
1. Unzip your downloaded FASTQ file with `gunzip *.fastq.gz`.
2. Inspect the first 10 lines of the FASTQ file with `head -10 ${YOUR_FASTQ}`.
   > What do you see? Does it align with the FASTQ format?


### Stage 6 - Clean up
1. Go back to the GitHub repo, click the green button `<> Code` and click `...` besides the active codespaces and then click `Delete`,
> [!CAUTION]
> Remember to DELETE the codespace, otherwise you will be charged for the usage of the codespaces.
