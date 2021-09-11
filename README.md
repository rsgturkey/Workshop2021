# Workshop2021
## ISCB RSG Turkey – Command Line Tools Workshop 2021

Linux is the most common operating system in the computational biology field. All basic and advanced tools and analysis algorithms are distributed in Linux environments such as omics analysis, structural biology, and evolutionary biology. Understanding the theory and basic concepts of the Linux operating system is one of the most critical cornerstones to start computational biology.

This workshop will teach you the theoretical background of the Linux environment, then basic Linux commands that are frequently used to navigate folders and files. After learning basic concepts and the most common commands, you’ll learn how to manipulate files with sed, awk and grep.

In this workshop, there will be both genomics and transcriptomic practical exercises where attendees can apply the knowledge that will have acquired in the previous sessions. The first session will focus on building de novo genome assembly using long-reads. The transcriptomic session will walk you through the first steps of analyzing RNA sequencing data, from getting raw sequencing files to visualizing the data on a genome browser and counting the features.

## Day 1: 12 September at 03:00 pm
## [Introduction to Linux and Theory (Instructor: Yiğit Koray Babal)](https://github.com/rsgturkey/Workshop2021/blob/main/Introduction_to_Linux_and_Theory/Linux_intro.md)

As an introduction to the Linux environment for newcomers in computational biology, firstly definition of the operating system and main components will be mentioned. Then, Windows and Linux operating system will be compared in different aspects along with why Linux is much more commonly used in computational biology will be discussed. As a final, how to switch your operating system into Linux will be mentioned with an example of Ubuntu installation (Desktop and/or virtual machine).

## [Command Line Basics (Instructor: Eda Şamiloğlu)](https://github.com/rsgturkey/Workshop2021/blob/main/Command_Line_Basics/Command_Line_Basics.pdf)

In this part, we will describe how the Linux file system is structured and learn how to use basic commands to navigate the file system. List of basic commands presented below.

- pwd
- cd
- man
- ls
- clear
- mkdir
- touch
- mv
- rm

Then we will introduce text editors, specifically nano. We will create a text file and modify it by using nano. Last but not least, we will demonstrate version control by using git.

## [Data Manipulation  (Instructor: Sevilay Güleşen)](https://github.com/rsgturkey/Workshop2021/blob/main/Data_Manipulation/data_manipulation.md)

In this section, we will work on basic data manipulation commands by using Bash. We will answer the following questions:

- How is the data file analyzed by using Bash?
- What are the basic commands for data manipulation?
- How does the bash script make this manipulation faster?
- What are the advantages of using Bash for simple operation?

 
## [Practical session I –  Introduction to Genome Assembly  (Instructor: Yasin Kaya)](https://github.com/rsgturkey/Workshop2021/blob/main/PS1_Introduction_to_Genome_Assembly/Intro2_denovo_assembly.md)

In this section, we will assemble a consensus genome using Illumina WGS data (filtered clean data). We will cover the de novo assembly of an organism without a reference genome by accurately mapping the short reads. In doing so, we will follow the steps below:

- Error correction of sequencing reads.
- K-mer size selection for genome assembly.
- Constructing a De Bruijn graph assembly for contigs.
- Statistical analysis of the assembled contigs.
- Visualizing the de novo assembly graph.

## Day 2: 13 September at 02:00 pm
## [Practical session II –  Introduction to RNA-seq Analysis (Instructor: Ravza Gür)](https://github.com/rsgturkey/Workshop2021/blob/main/PS2_Introduction_to_RNA-seq_Analysis)

In this session, we will analyze RNA sequencing data using command-line tools and commands.

We will cover the following analysis steps of RNA-seq:

- What are transcriptomics and RNA-seq?
- Getting familiar with technical concepts and data file formats
- Mapping sequencing reads to a reference genome using an aligner (STAR)
- Understanding the alignment file as an output of the mapping step
- Manipulating biological files via samtools
- Generating a bigwig file to upload to the UCSC Genome browser
- Counting number of reads that mapped to genes
