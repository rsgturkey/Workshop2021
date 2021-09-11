### ISCB RSG-Turkey Student Symposium - 12.09.2021 | Workshop Practical Session 1 
### Introduction to Genome Assembly     _by Yasin Kaya_
#


We will construct a  _de novo_  assembly of _Bacillus thuringiensis_ genome (filtered and reduced data and it contains ~2000-5000 reads). The raw data (actual size of the strain) contains 1.5G of data and the genome size is 6.4 mb.

#### Article of the genome
https://www.sciencedirect.com/science/article/abs/pii/S0168165615300961 
#### Assembly of the genome
https://www.ncbi.nlm.nih.gov/assembly/GCF_001182785.1 

> *Sequencing Platform:* Illumina HiSeq 2000 
Layout: paired-end 
Insert size (bp): 200
Read Length: 100 x 2

The two-day workshop sessions will be held in the Linux environment. So, we suggest you should have a terminal/console.  If you are not able to have a Linux distribution or any console. You can have it in various ways. For example, you can download an Ubuntu application from the [Windows store](https://www.microsoft.com/en-us/p/ubuntu/9nblggh4msv6?activetab=pivot:overviewtab) or install a [virtual machine with VirtualBox](https://www.youtube.com/watch?v=x5MhydijWmc) 

Second way is the portable edition (left side of the link -blue-) of the MobaXterm software.
https://mobaxterm.mobatek.net/download-home-edition.html 

The last and the best way is the using the Google Cloud Console. You can have an access with your gmail account and activate your cloud shell. 
https://console.cloud.google.com 

In addition, it is possible to have many softwares including bioinformatics pipeline from a single source. To install Miniconda, which contains many python packages, you can download the version that fits your system [from here](https://docs.conda.io/en/latest/miniconda.html). You don't have to worry about this part, in the first session of the workshop, the installation process will be explained by our instructors.

#### Obtain the course materials
You can access the raw data (*_named_* _bacillus_pe1.fastq,_ _bacillus_pe2.fastq_), assembled file (_bacillus_thu.fasta_) and zip file of the  QUAST softare from:
https://transfer.sh/zm6dxN/rsgturkey_assembly.zip 

You can download the course materials to your server/terminal/console:
```sh
wget https://transfer.sh/zm6dxN/rsgturkey_assembly.zip 
```

For the course to be carried out in a useful way, I suggest you follow the steps below before the course. If you have any questions, you can contact me without any hesitation (yyasinkkaya@gmail.com)

#### Error correction of sequencing reads 
#
To perform this step, you should install Karect software from conda. (for detail: [Conda Cheat Sheet](https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf) )
```sh
conda install -c bioconda karect
```
to run the Karect, you need to specify the conda environment path
```sh
~/miniconda3/bin/karect
```

Alternatively, you can try this installation method if conda does not work in your system.

```sh
wget https://github.com/aminallam/karect/archive/v1.0.zip
unzip v1.0.zip
cd karect-1.0
make
sudo mkdir -p /export/apps/karect/1.0/bin
sudo cp karect /export/apps/karect/1.0/bin
sudo cp LICENSE README /export/apps/karect/1.0
```

To run the Karect,
```sh
~$PATH/miniconda3/bin/karect -correct -threads=64 \
-matchtype=hamming \
-celltype=haploid \
-inputfile=./bacillus_pe1.fastq \
-inputfile=./bacillus_pe2.fastq \
-resultdir=./results -tempdir=./temp
```

#### Constructing a De Bruijn graph assembly for contigs.
#
You should install the [SPAdes](https://cab.spbu.ru/files/release3.12.0/manual.html) software (any version applicable)

installation from conda:

```sh
conda install -c bioconda spades
```

```sh
~$PATH/miniconda3/bin/spades.py -k 21,23,25,27 --only-assembler \
--12 bacillus.fastq \ #this file will be created during the workshop
--cov-cutoff auto -o out
```
#### Statistical analysis of the assembled contigs.
#
We'll download and use the [QUAST](http://bioinf.spbau.ru/quast) software.

You can try to install from conda but it's quitely possible to face the problem during the download/installation.
```sh
conda install -c bioconda quast
```
But you can visit and learn the details from their [Github](https://github.com/ablab/quast) page.

In case you are not able to install and run it properly, I uploaded the [rsgturkey_assembly.zip](https://transfer.sh/zm6dxN/rsgturkey_assembly.zip) file the useful version of the software
you can install it:
```sh
unzip rsgturkey_assembly.zip
tar xvf quast-5.1.0rc1.tar
cd quast-5.1.0rc1
./setup.py install
```

```sh
~$PATH/quast.py ./contigs.fasta \ #this file will be created during the workshop
-R ./bacillus_thu.fasta \
-o ./results
```
#### Visualizing the assembly graph.
#
We are going to use [Bandage](https://rrwick.github.io/Bandage/) software to display the assembled graph. This step will not be performed in console.

You can download the v0.8.1 version from: https://github.com/rrwick/Bandage/releases/ 

### If you don't want to deal with downloading all of them one by one, you can create your own environment with a single line of code.

```sh
conda create -n rsgturkey -c bioconda python=3.0 karect=1.0 spades=3.15.2 quast=5.0.2
```

To run the packages, firstly you need to activate your env.
```sh
conda activate rsgturkey 
```
To exit from the env, 

```sh
conda deactivate  
```

To remove the env,
```sh
conda env remove --name rsgturkey 
```
