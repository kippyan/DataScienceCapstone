# AWS DeepLens Camera Setup

Olivia Lund, Fall 2020

### This is a guide for configuring the Amazon Web Services DeepLens camera for use with this project. There are no requirements other than having the camera.


## 1. Registering the camera

To begin, navigate to [https://aws.amazon.com/deeplens/](https://aws.amazon.com/deeplens/).

![](./image/1.png)

From there, select "Register your DeepLens" to begin the process.

![](./image/2.png)

On the next page, select "Register device" to continue.

![](./image/3.png)

This prompts the user with a dialog box asking which version of the DeepLens is being used.

![](./image/4.png)

The next page is a set of very detailed instructions on carrying out the registration. Make sure to save the certificate, which is necessary for changing data on the device and will not be available again.


## 2: Creating a model to train the camera on

Before training can occur, a model is simply a collection of data, and needs to be stored somewhere. Amazon requires that training data be stored in an S3 bucket before training with it.

To set up the S3 bucket, from the Services menu on the main console, search for "S3" and enter the S3 console. 

![](./image/addthislater.png)

Once in the S3 console, select "Create a Bucket"

![](./image/addthislater.png)

From the bucket creation menu, create a name that follows the rules for bucket naming and select the nearest region. The rest of the settings can be left default.

![](./image/addthislater.png)

Now, from the S3 console, select the newly created bucket and click upload

![](./image/addthislater.png)

It's now time to add the data desired for training the model with.





To begin this project, I printed out 20 copies each of the pre-class and post-class survey, and filled them out by hand, using names from https://www.name-generator.org.uk/quick/ and somewhat random answers with different answering styles and different writing implements to ensure some variability. This will provide some robustness although in order to avoid heavy bias around my handwriting the model would need to be trained on forms filled out by many different people. 




## 3: Configuring the camera project

If registration was successful, navigating to [https://us-east-1.console.aws.amazon.com/deeplens/home?region=us-east-1#devices](https://us-east-1.console.aws.amazon.com/deeplens/home?region=us-east-1#devices) will look like the following image

![](./image/5.png)

Select the device to navigate to its details page

![](./image/6.png)

If the device registration failed, select "Deregister" and try the registration process again starting with section 1. 

If the registration was successful, select "Deploy a project"

![](./image/7.png)

The template projects are worth looking at, but their scope is very narrow. 







## 4: Creating a SageMaker training model


## 4.5: Creating an Execution Role
(basically just this https://docs.aws.amazon.com/sagemaker/latest/dg/onboard-quick-start.html)
[ 3 sagemaker studio screenshots]


Enter Sagemaker Studio

https://docs.aws.amazon.com/sagemaker/latest/dg/sagemaker-projects-create.html



