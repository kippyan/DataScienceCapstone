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

## 2. Configuring the camera project

If registration was successful, navigating to [https://us-east-1.console.aws.amazon.com/deeplens/home?region=us-east-1#devices](https://us-east-1.console.aws.amazon.com/deeplens/home?region=us-east-1#devices) will look like the following image

![](./image/5.png)

Select the device to navigate to its details page

![](./image/6.png)

If the device registration failed, select "Deregister" and try the registration process again starting with section 1. 

If the registration was successful, select "Deploy a project"

![](./image/7.png)

The template projects are worth looking at, but their scope is very narrow. 


