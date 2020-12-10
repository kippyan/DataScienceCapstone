# AWS DeepLens Camera Setup

Olivia Lund, Fall 2020

### This is a guide for configuring the Amazon Web Services DeepLens camera for use with this project. There are no requirements other than having the camera.



## 1. Prep work 

### 1.1: Registering the camera

To begin, navigate to [https://aws.amazon.com/deeplens/](https://aws.amazon.com/deeplens/).

![](./image/1.png)

From there, select "Register your DeepLens" to begin the process.

![](./image/2.png)

On the next page, select "Register device" to continue.

![](./image/3.png)

This prompts the user with a dialog box asking which version of the DeepLens is being used.

![](./image/4.png)

The next page is a set of very detailed instructions on carrying out the registration. Make sure to save the certificate, which is necessary for changing data on the device and will not be available again.



## 1.2: Configuring the camera project

If registration was successful, navigating to [https://us-east-1.console.aws.amazon.com/deeplens/home?region=us-east-1#devices](https://us-east-1.console.aws.amazon.com/deeplens/home?region=us-east-1#devices) will look like the following image

![](./image/5.png)

Select the device to navigate to its details page

![](./image/6.png)

If the device registration failed, select "Deregister" and try the registration process again starting with section 1. 

If the registration was successful, select "Deploy a project"

![](./image/7.png)

The template projects are worth looking at, but their scope is very narrow. In order to fulfill the requirements of this project, it will be necessary to create and train a new model. 


## 1.3: Requesting a service limit increase for training models

The standard VMs provided by AWS lack the powerful GPU that is necessary for training a SageMaker model, and as a result a request ticket has to be created. First, navigate to [https://console.aws.amazon.com/support/home#/case/create](https://console.aws.amazon.com/support/home#/case/create) and select Service Limit Increase

![](./image/19.png)



## 2: Creating a training model

For tjis section, this guide was immensely helpful for learning how to get started:
[https://docs.aws.amazon.com/deeplens/latest/dg/deeplens-getting-started-hard.html](https://docs.aws.amazon.com/deeplens/latest/dg/deeplens-getting-started-hard.html)


### 2.1: Creating a storage container to store training data in

Before training can occur, a model is simply a collection of data, and needs to be stored somewhere. Amazon requires that training data be stored in an S3 bucket before training with it.

To set up the S3 bucket, from the Services menu on the main console, search for "S3" and enter the S3 console. 

![](./image/8.png)

Once in the S3 console, select "Create a Bucket"

![](./image/9.png)

From the bucket creation menu, create a name that follows the rules for bucket naming and select the nearest region. The rest of the settings can be left default.

![](./image/10.png)

Now, from the S3 console, select the newly created bucket and click upload:

![](./image/11.png)

It's now possible to add the data desired for training the model with.



### 2.2: Entering the Sagemaker Studio

From the AWS services menu, select SageMaker studio from under Machine Learning:

![](./image/12.png)

In order to enter the studio, a SageMaker specific account will have to be created:

![](./image/13.png)

A user IAM role will have to be created as well, if one wasn't created in order to enter the S3 console in step 2.1:

![](./image/14.png)

Fortunately, this is relatively straightforwards, and all permissions can be left default:

![](./image/15.png)

After hitting "Create Role", this screen should appear:

![](./image/16.png)

Once this is complete, after a brief readying period, it should be possible to select "Open Studio" from the far right of the window:

![](./image/17.png)

The studio should show a characteristic dark background as such:

![](./image/18.png)



### 2.3: Requesting Additional Resources








To begin this project, I printed out 20 copies each of the pre-class and post-class survey, and filled them out by hand, using names from https://www.name-generator.org.uk/quick/ and somewhat random answers with different answering styles and different writing implements to ensure some variability. This will provide some robustness although in order to avoid heavy bias around my handwriting the model would need to be trained on forms filled out by many different people. 






It required getting anaconda working and after some poking around about why it didn't work I found out that I needed to run this:
sudo wget https://repo.continuum.io/miniconda/Miniconda2-latest-Linux-x86\_64.sh
bash Miniconda2-latest-Linux-x86\_64.sh

i was prompted to do 
$conda update -n base -c defaults conda
and then i had a weird issue where my terminal was preceeded with (base) so i did conda config and added 'changeps1: False' to it and reboot which fixed it

conda create -n "py3.9" python=3.9.0
conda activate py3.9
conda install conda=4.9.2

In running deeplens-hotdog-or-not i had to change the url of the "not a dog image" because it was dead. I had to read through the error log to find this out.

I went through making three different python environments with different versions until I got far enough back that all the dependencies of the hotdog code worked

change block 6 line 3 to be:
wget -O scroll001.jpg https://bingvsdevportalprodgbl.blob.core.windows.net/demo-images/876bb7a8-e8dd-4e36-ab3a-f0b9aba942e5.jpg
image is arbitrary

Need to follow this guide https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html#cli-configure-quickstart-creds to get the last bit of the code to run.




