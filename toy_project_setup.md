## Toy Project Setup

### This file documents the issues and fixes involved with creating the DeepLens training program following this guide:
[https://aws.amazon.com/getting-started/tutorials/build-deeplens-project-sagemaker/](https://aws.amazon.com/getting-started/tutorials/build-deeplens-project-sagemaker/)


It required getting anaconda working and after some poking around about why it didn't work I found out that I needed to run this:
sudo wget https://repo.continuum.io/miniconda/Miniconda2-latest-Linux-x86\_64.sh
bash Miniconda2-latest-Linux-x86\_64.sh

I was prompted to do:
$conda update -n base -c defaults conda
and then I had a weird issue where my terminal was preceeded with (base) so i did conda config and added 'changeps1: False' to it and reboot which fixed it

conda create -n "py3.7" python=3.7.5
conda activate py3.7
conda install conda=4.9.2

In addition, there were several packages that the program identified as missing while starting up the code. Each of these had to be manually added to the py3.7 environment using conda.

In running deeplens-hotdog-or-not i had to change the url of the "not a dog image" because it was dead. I had to read through the error log to find this out.
That was accomplished by changing block 6 line 3 to be:
wget -O scroll001.jpg https://bingvsdevportalprodgbl.blob.core.windows.net/demo-images/876bb7a8-e8dd-4e36-ab3a-f0b9aba942e5.jpg
The image I chose happened to be of a domestic dog but it's arbitrary.

I needed to follow this guide [https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html#cli-configure-quickstart-creds](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html#cli-configure-quickstart-creds) to get the last bit of the code to run.



