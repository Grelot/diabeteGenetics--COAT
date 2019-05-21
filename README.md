# CoverageAnalysisTool

Outputs a list of coding regions that are uncovered above a given threshold

# Overview

The output is a spreadsheet with all the coding regions which are uncovered.
Supplementary annotation can be used for further analysis. Additional files can be
generated using `--cover_output` argument and/or `--track_no_cover_UCSC_output`.

# Input

## BAM files

BAM is a binary file format. SAM and BAM files contain the same information. These
files contain mapped reads sequence from Next Generation Sequencing.

# Installing COAT on LINUX

To use COAT, the following programs are necessary  :

* [python 2.6](https://www.python.org/download/releases/2.6/)
* [samtools 1.3](https://sourceforge.net/projects/samtools/files/samtools/1.3/)

The following files are necessary :

* BAM files folder
* reference sequence annotation file

## Programming language Python

Python (version 2.6.5 to version 2.7.8). To see which version of Python you have
installed, open a command prompt and run:

```
python --version
```

If you don’t have Python, type the following command to install python version 2.x:

```
sudo apt-get install python 2.6

```

## Samtools

To run COAT, you must have installed [samtools 1.3](https://sourceforge.net/projects/samtools/files/samtools/1.3/). If you have a previous version of samtools, COAT will not work, so download and install samtools 1.3. Unzip the downloaded file. Go into the newly created directory and compile the code by typing "make".

```
tar -xvjf samtools-1.3.tar.bz2
cd samtools-1.3/
make
```

## BAM

Store your BAM files into a dedicated folder. Prefix of BAM files name is used as subject identifier (see command-line argument `--subject_list`).

<img src="https://github.com/Grelot/diabeteGenetics--COAT/blob/master/images/bam_schema_folder.png"  title="bam_schema_folder">

Samtools folder must be specified (see command-line argument `--samtoolsPath`)
BAM files must be indexed. To generate Index of BAM files, use samtools line-commands:

```
samtools sort -T /tmp/aln.sorted -o aln.sorted.bam aln.bam
samtools index aln.sorted.bam
```

## Reference sequence annotation file

Reference annotated sequence is needed. This file contains gene	annotation of the genome reference you want to use. You can get file for h19 reference:
- http://hgdownload.cse.ucsc.edu/goldenPath/hg19/database/refFlat.txt.gz

# Command-line Arguments

| complete flag argument | short flag |Default value | Summary |
| --- | --- | --- | --- |
| `--output` | `-o` | stdout | Output folder path. Will overwrite contents if file exists. |
| Select region |
| `--position | `-p` | _NA_ | Interval positions in chromosome of the reference sequence 
FORMAT: _chr:start-end_ |







