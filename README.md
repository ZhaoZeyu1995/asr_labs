# Automatic Speech Recognition (INFR 11033) Labs 

## Setup for labs

The Informatics computing labs use DICE, a Linux environment.
If you are not familiar with Linux and its basic usage, you might find [this webpage](https://computing.help.inf.ed.ac.uk/linux) helpful.

All the labs are in Python with Jupyter Notebook so that you can edit and run your code in a browser
If you would prefer to edit your code directly with any other text editors or development tools, this is fine too.

Each lab has its own Jupyter Notebook file, named `asr_labX.ipynb`, except Labs 3 and 4 sharing one file.

****

### Commands for setting up the Python environment

At the beginning of the first lab, you will need to set up your Python environment.
This can be used for subsequent weeks of labs, so these commands only need to be run once.

Here are the commands for setting up the environment.
These commands have been tested on DICE, and work in most other computing environments (with minor changes, possibly)

```shell
git clone https://github.com/ZhaoZeyu1995/asr_labs.git
cd asr_labs
source /opt/conda/etc/profile.d/conda.sh
conda create -n asr_env python=3.7
conda activate asr_env
pip install openfst-python jupyter
```

**NOTE: You will need to run some other commands to sync later weeks’ lab exercises when they become available.**

****

### Working on a computer in the lab in-person (the recommended way of working)

1.  Log in to a computer with your DICE account and password
2.  Run the commands for setting up the environment above.

Now we have set up the environment for our labs. 
From now on, every time we log in, we just need to run the following commands.

```shell
source /opt/conda/etc/profile.d/conda.sh 
cd asr_labs ## if you are not in this directory already
conda activate asr_env 
jupyter notebook
```

After running the last command, the default browser will be opened automatically and you can view and open any files with Jupyter Notebook. 
First, the only the notebook for Lab 1 will be available, and you will need to run the command `git pull` in the `asr_labs` directory to update your copy to the latest version.
This will also allow you to obtain the solutions of the last lab, and possibly file amendments or bug fixes. 

If you are not familiar with Git, the safest thing to do is to make a copy of the file you would like to edit (e.g. to make a copy of `asr_lab1.ipynb`, you can run `cp asr_lab1.ipynb asr_lab1_copied.ipynb`) and only make changes and run the code in the copied files (`asr_lab1_copied.ipynb` in the example). 
To get updates, all you need to do is to run `git pull` in the `asr_labs` directory (of course, you will have to `cd` to this directory first).

You are recommended to run `git pull` every time you `cd asr_labs` to obtain the latest version.

**NOTE: When you run `git pull`, you may get an error similar to below**

```
error: Your local changes to the following files would be overwritten by merge:
 asr_lab1.ipynb
Please commit your changes or stash them before you merge.
Aborting
```

In this case, you can run

```
git stash
```

which stashes your changes to this repository. 

After that, you can run

```
git pull
git stash pop
```

which will update your local version to the one on Github and then merge the changes you made. 
You can view all the changes we made and the new files we uploaded to the repository on your machine now.
If you continue to receive warning or error messages at this stage, please get advice from a lab demonstrator.

**NOTE: If you are not familiar with Git, it is safest to create a backup copy of all your files before doing this.**

****

### Working directly in Python

If you are an experienced Python developer and prefer to work directly with Python instead of Jupyter Notebook, this is fine.
To convert a notebook file to pure Python code, you can run

```
jupyter nbconvert --to python asr_labX.ipynb
```

Just replace the final argument with the name of the notebook you wish to convert.

### Working remotely

Although it's not recommended until you have become familiar with the working environment for the labs, it is possible to access them for a remote working. 
Please refer to [Remote Working](RemoteSetup.md)
