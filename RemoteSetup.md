# Remote working (not recommended)

There are three main options for working on the labs and assignment remotely or on your own laptop.

1.  Use the [remote desktop service](https://computing.help.inf.ed.ac.uk/remote-desktop)
2.  Use the [informatics VPN](https://computing.help.inf.ed.ac.uk/openvpn)
3.  Run the code directly on your own PC or Mac (not recommended as different problems may occur).

## Remote desktop

1.  Set up the [remote desktop service](http://computing.help.inf.ed.ac.uk/remote-desktop)
2.  Connect to a remote desktop
3.  Open a terminal on the remote desktop
4.  Run `ssh s1234567.lab.inf.ed.ac.uk` (replacing the student ID with your own). Please try `ssh student.compute.inf.ed.ac.uk` instead, if the former does not work for you.
5.  Run the [commands for setting up the environment](README.md#commands-for-setting-up-the-python-environment)

After the above is finished, every time you log in, you only need to run the following commands.

```shell
source /opt/conda/etc/profile.d/conda.sh 
cd asr_labs ## if you are not in this directory
conda activate asr_env 
jupyter notebook --ip=*
```

If the token is not working, `jupyter notebook password` lets you set a password.

## Informatics VPN

1.  Set up the [informatics VPN](https://computing.help.inf.ed.ac.uk/openvpn) 
2.  Connect to the VPN
3.  Open a terminal
4.  Run `ssh s1234567@s1234567.lab.inf.ed.uk` (please try `ssh s1234567@student.compute.inf.ed.ac.uk` or `ssh student.ssh.inf.ed.ac.uk` if the former does not work for you).
5.  Enter your DICE password
6.  Run `ssh student.compute`
7.  Run the [commands for setting up the environment](README.md#commands-for-setting-up-the-python-environment)

From now on, every time you log in, you only need to run the following commands

```shell
source /opt/conda/etc/profile.d/conda.sh
cd asr_labs ## if you are not in this directory
conda activate asr_env
jupyter notebook --no-browser --ip=*
```

**NOTE: there is a `--no-browser` added in the last command.**

## Run Jupyter on your own PC or Mac (NOT RECOMMENDED)

Before this, you might need to check if [openfst](https://www.openfst.org/twiki/bin/view/FST/WebHome) and [openfst-python](https://pypi.org/project/openfst-python/) are compatible with your operating system. 
Please make sure of this before you do the following.

1.  Install [anaconda](https://www.anaconda.com/)
2.  Open a terminal
3.  Install [openfst](https://www.openfst.org/twiki/bin/view/FST/WebHome) and [graphviz](https://graphviz.org/) by `conda install -c conda-forge openfst`and `conda install graphviz`
4.  Run the [commands for setting up the environment](README.md#commands-for-setting-up-the-python-environment) but omit `source /opt/conda/etc/profile.d/conda.sh`

After setting up the environment, we may run
```shell
cd asr_labs ## if you are not in this directory
conda activate asr_env
jupyter notebook --no-browser
```

and open the link returned by Jupyter notebook. 
If this does not work well, we think the easiest option is to use the [remote desktop](#remote-desktop), while the VPN and the SSH tunnel will give you the most responsive experience. 
Running Jupyter on your personal machine is not recommended, but you can do it, in a pinch, for the first few labs.
The files we will use for the assignment are on the school’s AFS filesystem and can’t be copied locally for data protection. While it is possible to have [AFS on your personal machine](http://computing.help.inf.ed.ac.uk/informatics-filesystem), it’s a bit complicated, and we are not able to provide any support for this. 
We suggest you do this set-up a few days before the lab starts, so it’s ready for the lab day. 
Leave some time for troubleshooting and dealing with problems that might crop up.

****
