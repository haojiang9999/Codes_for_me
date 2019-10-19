
####  Before activating an environment it might be good to do a
https://stackoverflow.com/questions/17386880/does-anaconda-create-a-separate-pythonpath-variable-for-each-new-environment
```
unset PYTHONPATH
```
#### Installing an older version of R in a conda environment
http://salvatoregiorgi.com/blog/2018/10/16/installing-an-older-version-of-r-in-a-conda-environment/
```
#First we create a new environment:

> conda create -n myRenv3_4 anaconda
#and then switch to the new environment with:

> source activate myRenv3_4
#To confirm we have this running properly we can ask where the pip command will run from (hopefully it is tied to a location inside our environment):

> which pip
/anaconda/envs/myRenv3_4/bin/pip
Note that R is not installed by default inside the environment:

> which R
/usr/bin/R
Next we search for the R version we want to install. Because conda’s search will match any packages that contain our search term as a substring (in our case the letter “r”) we search instead for “r-base”:

> conda search r-base
Now that we’ve confirmed the package/version we want is available we R v3.4.1 with the following:

> conda install -c conda-forge r=3.4.1
One can also try installed with -c r instead of conda-forge but I’ve found that not all versions are available via r.

To confirm that this installed properly (you might have to source deactivate and source activate to get :

> which R
/anaconda/envs/myRenv3_4/bin/R
When we open R we should see the following:

> R
R version 3.4.1 (2017-06-30) -- "Single Candle"
but on some installs I’ve seen the following error:

> R
/anaconda/envs/myRenv3_4/lib/R/bin/exec/R: symbol lookup error: /anaconda/envs/myRenv3_4/lib/R/bin/exec/../../lib/../../libreadline.so.6: undefined symbol: PC
This can be fixed with an update to the readline package (see this ticket for more info):

> conda install -c conda-forge readline=6.2
Next, the Native R kernel for Jupyter is installed with:

> conda install -c r r-irkernel

> conda uninstall r-base
uninstall r-essentials using conda?
which R

```
#### add coda-foge to conda
https://conda-forge.org/#about
```
conda config --add channels conda-forge 
conda config --set channel_priority strict 
conda install <package-name>
```
#### Install requered package by conda
```
conda install -n OpenNE --file requirements.txt
```
#### Create virtual environments for python with conda
https://uoa-eresearch.github.io/eresearch-cookbook/recipe/2014/11/20/conda/
1. Check conda is installed and in your PATH
Open a terminal client.
Enter conda -V into the terminal command line and press enter.
If conda is installed you should see somehting like the following.
```
$ conda -V
conda 3.7.0
```
2. Check conda is up to date
In the terminal client enter
```
conda update conda
```
3. Create a virtual environment for your project
In the terminal client enter the following where yourenvname is the name you want to call your environment, and replace x.x with the Python version you wish to use. (To see a list of available python versions first, type conda search "^python$" and press enter.)
```
conda create -n yourenvname python=x.x anaconda
```
4. Activate your virtual environment.
To activate or switch into your virtual environment, simply type the following where yourenvname is the name you gave to your environement at creation.
```
source activate yourenvname
```
5. Install additional Python packages to a virtual environment.
To install additional packages only to your virtual environment, enter the following command where yourenvname is the name of your environemnt, and [package] is the name of the package you wish to install. Failure to specify “-n yourenvname” will install the package to the root Python installation.
```
conda install -n yourenvname [package]
```
6. Deactivate your virtual environment.
To end a session in the current environment, enter the following. There is no need to specify the envname - which ever is currently active will be deactivated, and the PATH and shell variables will be returned to normal.
```
source deactivate
```
6. Delete a no longer needed virtual environment
To delete a conda environment, enter the following, where yourenvname is the name of the environment you wish to delete.
```
conda remove -n yourenvname -all
```
