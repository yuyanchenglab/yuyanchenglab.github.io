---
layout: default
title: Intro to Programming
nav_order: 2
parent: Intro to Computation
has_children: false
---

# {{page.title}}

In your .bashrc file in your home directory on the HPC server, I suggest you place these lines: 

```
if [ $HOSTNAME != "consign.hpc.local" ] &&
   [ $HOSTNAME != "mercury.pmacs.upenn.edu" ] &&
   [ $HOSTNAME != "hpclogin.pmacs.upenn.edu" ] &&
   [ $HOSTNAME != "hpclogin1" ]; then
    module load R4.3
    module load python/3.11
    module load sratoolkit/3.1.0
    module load curl
    module load fastqc/0.11.7
fi 
```

This way, we are all working on the same version of R and python and so that you can use some commonly used tools without thinking about it in the future.

There is some software that we've locally installed for the lab, and you can use it by adding this to your .bashrc file:

```
LAB_SOFTWARE="/project/hipaa_ycheng11lab/software/"
SOFTBIN="${LAB_SOFTWARE}/bin/"
PATH=$SOFTBIN:$PATH
export PATH # This line goes after all of your other PATH stuff

export CPATH=$LAB_SOFTWARE/include:$CPATH
export LD_LIBRARY_PATH=$LAB_SOFTWARE/lib:$LD_LIBRARY_PATH
export LIBRARY_PATH=$LAB_SOFTWARE/lib:$LIBRARY_PATH

export PYTHONPATH=/project/hipaa_ycheng11lab/software/python/lib/python3.11/site-packages/:/project/hipaa_ycheng11lab/software/python/bin/:$PYTHONPATH
```

When coding, we also want to have coding buddies. This will be something we explore in the future.

## Intro to the Command Line

### Computing through VPN

To access the PMACS cluster, you must have the VPN installed. Use the following PDFs to install the VPN:

* PC: [link](https://www.med.upenn.edu/pmacs/assets/user-content/documents/pmacs-vpn-windows-automated-install-and-configuration-(preferred).pdf)
* Mac: [link](https://www.med.upenn.edu/pmacs/assets/user-content/documents/pmacs-vpn-mac-os-automated-install-and-configuration-(preferred).pdf)

The instructions are slightly outdated as we no longer use the Pulse Secure client and instead use the Ivanti Secure Access client with the following icon:

<img src="/assets/images/IvantiSecureAccessIcon.webp" alt="drawing" width="50"/>

Everytime you connect to the VPN, it will ask for two factor authentication. There are three options:

* Duo Push to phone_push (iOS)
* Phone call to XXX-XXX-XXXX
* SMS passcodes to XXX-XXX-XXXX

Enter the number of your desired authentication method and complete the authentication. You should be connected afterwards. 

If there are any issues with your VPN connection, try the following. If one of these is unsuccessful, continue to the next one.

* Restart the client
* Add a new connection with remote.pmacs.upenn.edu as the server URL
* Follow the steps at this [link](https://forums.ivanti.com/s/article/Deep-Clean-Procedure-for-Windows-and-MAC?language=en_US) to uninstall and then reinstall the VPN.


### Logging in

If this is your first time logging in, follow the steps listed on the HPC wiki [here](https://hpcwiki.pmacs.upenn.edu/index.php/HPC:Login#First_Login).

Otherwise, in your computer’s terminal, run the following command:

    $ ssh <PMACS_ID>@consign.pmacs.upenn.edu

Make sure to insert your own PMACS ID to replace <PMACS_ID>. 
It will then ask for your PMACS password. You won't see anything typing, but press Enter after you've typed out your password. You should then see the login screen and be in your home directory on the server.

If you are not asked for your password and the request eventually times out, make sure that you  are connected to the VPN. 

### Interactive Nodes

For the next two sections, the directions will mirror those in the [HPC User Guide](https://hpcwiki.pmacs.upenn.edu/wiki/index.php/HPC:User_Guide). I would suggest looking through the guide for more information. 

If you have a compute-intensive job, you should use an interactive node to run it rather than running it directly on the cluster head node (consign.pmacs.upenn.edu).

To request an interactive node, run the following command.

    $ bsub -Is bash

Most likely, you will want to request more memory or cores for this larger job. Here is an example:

    $ bsub -n 4 -R "rusage[mem=75000] span[hosts=1]" -M 75000 -Is bash

For descriptions of the added parameters, refer to the table in the [Submitting Jobs](https://yuyanchenglab.github.io/docs/Intro%20to%20Computation/Programming.html#Submitting%20Jobs) section.

If you are requesting an interactive node to use a Jupyter notebook within the node, there are additional steps. The process below is for Mac users. For other devices, follow the steps [here](https://hpcwiki.pmacs.upenn.edu/wiki/index.php/HPC:Jupyter).

* Navigate to the root directory of your work. All of the files you need access to should be here or in a subdirectory.
* Within an interactive node with the necessary resources requested, run the following command:

    [<your_username>@node### ~]$ jupyter notebook --ip $(hostname)

* Next, you need to setup an SSH tunnel to the Jupyter notebook session in a another local terminal with the following command:

        $ ssh -L 8888:node###:8888 <your_username>@consign.pmacs.upenn.edu

    Make sure to change ### and <your_username> to the node name and your username, respectively. Sometimes, the notebook's port is not 8888, so be aware of that.
* You should be able to get to your jupyter notebook session by accessing the localhost specific link generated in the output of the `jupyter notebook --ip $(hostname)` command. The link that starts with "http://127.0.0.1". Note that this is a unique URL for this session only.


### Submitting Jobs

To run shell scripts, the most basic way is to run the following command.
 $ bsub <script_name> 
However, there are many parameters that could be added. Here is a relevant example:

    $ bsub -J IHRA_markers -e IHRA_markers.%J.error -n 8 -R -M 1024 'rusage[mem=1024] span[hosts=1]' bash IHRA_gene_marker_predicates.bash
 
Descriptions of parameters:

-J IHRA_markers
LSF job name
-o IHRA_markers.%J.out
Name of the job output file (necessary to receive an output file)
-e IHRA_markers.%J.error
Name of the job error file (necessary to receive an error file)
-n 8
Number of cores requested
-M 1024
MB of memory for this job
-R 'rusage[mem=1024] span[hosts=1]'
Make sure the job's assigned node has enough memory and that all cores are on the same worker node
bash
Job type
IHRA_gene_marker_predicates.bash
Script name

Alternatively, to run LSF job scripts, run the following command:

    $ bsub < <script_name>

The job's parameters are in the header of the file itself. Here is a generic one of these scripts:

    #!/bin/bash
    #BSUB -J JNAME           
    #BSUB -o JNAME.%J.out     
    #BSUB -e JNAME.%J.error   
    #BSUB -n 1                 
    #BSUB -M 10              
    #BSUB -R "rusage[mem=10] span[hosts=1]"
    #BSUB -notify done         # Whenever the job finishes, email
    #BSUB -u <username>@pennmedicine.upenn.edu # User's email, both this and above are required for emails

    echo "hello"

## Intro to Python

## Intro to R

Quite a lot of biostat packages are run in R for a few reasons: 

* CRAN
* Statistics oriented syntax
* Rstudio

CRAN stands for the “Comprehensive R Archive Network” and is where you are likely to find additional R code for your use. By simply performing `installPackages(“magittr”)` in the R interpretter, R will go to CRAN through your internet connection and install that package for you. All you have to do is `library(magittr)` all of the magittr package is available to you! 

R is statistically oriented in quite a few different ways. The base package that is loaded for you when you open R contains native operators for linear algebra and set operations, such as %in% for testing set intersection and %o% for outer products. It has a base system of plotting and quickly creating test data, such as the built-in datasets and the r* distribution functions. 

Rstudio is the IDE that has everything you would want to run, troubleshoot and profile code. It allows you to run your code right from the source editor. Feel free to customize the look of your Rstudio to fit your needs. 

If you are using a large dataset, remember that the Rstudio server that you should have access has a limit of 20GB of memory. If you need to use more than that, you must use an interactive session with enough memory and use the command line. If you figure out how to run your own Rstudio server on the HPC to tunnel into, reach out to Jeff at Jeffrey.Maurer@pennmedicine.upenn.edu or reach out less formally in Slack. 