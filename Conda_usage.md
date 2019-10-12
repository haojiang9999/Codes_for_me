

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
