### Deploy on Tenzar DX

This walkthrough will cover the details of deployments on Tenzar. You can follow along from your Dashboard. This assumes you've already completed the Getting Started and Tenzar Terminal tutorials.

#### Deployment basics

A deployment is an ephemeral instance ("a server") in the cloud that you use to run your workload. When you launch a deployment on Tenzar DX, the Tenzar Engine will do the following automatically:

1.  Spin up a Virtual Private Server (VPS) on a cloud infrastructure provider
2.  Configure compute, storage, security settings and more
3.  Transfer your image and volumes to the instance
4.  Run your image as a Docker container on the deployment
5.  Enable SSH so you can easily connect to the deployment

To launch a deployment, first go to the console in your Dashboard. This tutorial will explain each line of the deployment form.

<center>
  <img src="https://s3.amazonaws.com/assets.tenzar.com/docs/deploy--deploy.png" width="450" alt="deploy"/>
</center>
<br/>

This deployment can also be launched directly from the terminal:

```text
$ tt deploy --image tensorflow-gpu --type GC1 --name image-rec --storage 150 101_ObjectCategories.tar.gz tensorflow-models images
```

##### Image

This is the underlying operating system that your deployment will run. You can only select one image and it cannot be changed once the deployment is launched.

I want to run a Tensorflow model on a GPU instance, so I'm going to select the `tensorflow-gpu` image that I imported from `tensorflow/tensorflow:latest-gpu`. Only images that were built for GPUs will be able to access the GPU resources of an instance. Most popular computing frameworks already have gpu-enabled images on DockerHub. If you need to use an image that does not come with GPU drivers preinstalled, you'll have to install nvidia-smi on the instance if you want to access GPU resources.

You can also select a default image on the images page in the Dashboard. A default image is 'preselected' to run your deployments in the future. This is purely for convenience and the image can always be changed before deploying. Simply click the menu icon next to the image you want to set as default. A star will appear next to the image name to indicate it's my team's default.

<center>
  <img src="https://s3.amazonaws.com/assets.tenzar.com/docs/deploy--set-default.png" width="500" alt="set default"/>
</center>
<br/>

##### Instance

For GPU deployments I have two instance types to select from: 1 or 8 GPUs. In this case, I don't need all the resources or speed of the GC8 so I'll select a the GC1.

When you don't need a GPU, the Compute instances offer the highest performance processors for compute-intensive tasks. The Standard and Memory instances have less performance per core but are ideal for tasks that have higher memory requirements.

You can see a breakdown of all our instance offerings on the Instance Types page.

##### Volumes

Here I specify the exact Volumes I want to use in my computation. I imported the Tensorflow models file from [Github](https://github.com/tensorflow/models) (you can click 'Clone or download' and 'download ZIP' to get the link to import) and an image recognition dataset from the [Caltech Vision webpage](http://www.vision.caltech.edu/Image_Datasets/Caltech101/). I'm also including a folder of images that I uploaded through the terminal.

These volumes will be automatically downloaded to my deployment when it is launched.

##### Name

The name field is for convenience - a way to label deployments to easily identify which is which. It's also a way to reference the deployment in the terminal and re-use commands, for instance:

```text
$ tt put image-rec /tmp/config.yml /root/conf.yml
```

If you stop the deployment and start another one with the same name, this command will act on the new deployment. It allows me to write scripts to control deployments or re-use my terminal history to run the same things again.

##### Extra Space

Every deployment on Tenzar comes with a minimum of 20 GB free disk space. For example, if my image is 5 GB and my volumes total 30 GB, the deployment will start with at least 55 GB of disk space, allowing me 20 GB to use.

If I want more than 20 GB, I can enter what I need in the 'Extra Space' field. In this case I'll have a total of 170 GB free - 150 GB 'extra'.

##### Preview

Once you click 'Deploy', the preview will confirm what you're about to do. Use this screen to make sure your instance type, image, and volumes are correct.

'Total Data Size' denotes the total size of the images and volumes you're deploying with. 'Disk Space' is the amount of storage we'll provision. And finally, 'Price' is the cost per minute to run your deployment. It is the sum of a few parameters:

1.  Instance price
2.  Container runtime
3.  Storage costs

Prices for these can be seen on the [Pricing page](/pricing). Note that even though the container runtime price is included in this number, it will not be billed until your deployment is running and ready to use.

Finally, 'Approximate setup time' is our estimate for how long it will take your deployment to launch. It's a function of how long is typically takes to spin up and instance plus the time it should take to transfer your data and run the container.

<center>
  <img src="https://s3.amazonaws.com/assets.tenzar.com/docs/deploy--preview-launch.png" width="300" alt="preview deployment"/>
</center>
<br/>

##### Monitor the Deployment

Once you click 'Deploy' on the preview pane, you'll be taken to the Deployments page. You can also see this information in the terminal by typing `tt monitor`.

<center>
  <img src="https://s3.amazonaws.com/assets.tenzar.com/docs/deploy--deployments.png" width="500" alt="deployments"/>
</center>
<br/>

This page will monitor the progress of your deployment. It automatically refreshes so you can keep the page open and watch the status. 'Pending' means we're spinning up an instance in the cloud, 'provisioning' means we're transferring your data and configuring your containers, and finally 'running' means the deployment is booted up and ready to use.

Clicking on the deployment in this window will bring up some information about it. 'Cost' updates in real time and will tell you the total cost of the deployment for the time it's been running.

<center>
  <img src="https://s3.amazonaws.com/assets.tenzar.com/docs/deploy--deployments-sidebar.png" width="150" alt="sidebar"/>
</center>
<br/>

##### Connect

Once your deployment is in the 'running' state, you can connect to it from the Terminal, add files to it, and more. This is covered in the Tenzar Terminal tutorial. Now that we have a name for the deployment we can connect to it in three ways:

`tt connect` if this is your only running deployment

`tt connect 5aa` to using the unique deployment ID

`tt connect image-rec` using the deployment name

##### Destroy

When you're done with your deployment and you've saved the files you need, click 'Destroy' on the Dashboard to terminate your instance (you'll be prompted to confirm first). You will no longer be charged for a deployment once you destroy it.

<center>
  <img src="https://s3.amazonaws.com/assets.tenzar.com/docs/deploy--destroy.png" width="500" alt="destroy deployment/>
</center>
<br/>

You can destroy a deployment from the terminal as well:

```text
$ tt destroy image-rec
```
