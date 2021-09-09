# Introduction to Linux and Theory (Instructor: Yiğit Koray Babal)
## Workshop Instructions

Within the scope of this workshop, 2 different ways are suggested for the initial installation of the linux environment.

### 1. Windows Subsystem for Linux (WSL)

[Installation manual](https://docs.microsoft.com/en-us/windows/wsl/install-win10)

**Note:** To install WSL on Windows 10, Virtual Machine Feature must be enabled. For this, you can refer to [here](https://docs.microsoft.com/tr-tr/windows/wsl/install-win10#step-2---check-requirements-for-running-wsl-2)

### 2. Ubuntu Installation on Virtual Box

Ubuntu 20.04 LTS installation on Virtual Box will be represented in workshop session. All required links are also listed below.

[Virtual Box Download link](https://www.virtualbox.org/wiki/Downloads)

[Ubuntu 20.04 LTS Download link](https://ubuntu.com/download/desktop)

[Installation procedures](https://www.wikihow.com/Install-Ubuntu-on-VirtualBox)

## Basic commands in Linux terminal

**Command** | **Definition**
---:|:---
sudo apt update | Update package repository
sudo apt upgrade | Upgrade all software and packages
sudo apt install <package_name> | Install the <package_name>
sudo apt remove <package_name> | Remove the <package_name>
sudo apt search <package_name> | Search the <package_name> into repository

## Conda Installation

Conda is an open-source package management system and environment management system that runs on Windows, macOS, and Linux. Using conda environment the most of tools and packages required for any computational biology analyses can be installed. The minimal version of conda can be installed by Linux terminal are given below:

    cd Downloads/
    wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
    ./Miniconda3-latest-Linux-x86_64.sh

For additionall installation documentation, you can refer [here](https://conda.io/projects/conda/en/latest/user-guide/install/linux.html)

Activating Bioconda environment after conda installation:

    conda config --add channels defaults
    conda config --add channels bioconda
    conda config --add channels conda-forge
   
Now Bioconda is enabled. For install conda packages/tools can be installed with:

    conda install bwa
    
 For extensive conda usage, conda cheatsheet can be downloaded from [here](https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf)

