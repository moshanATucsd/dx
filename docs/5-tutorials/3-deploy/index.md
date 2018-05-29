### Deploy on Tenzar DX

This walkthrough will cover the details of deployments on Tenzar DX. You can follow along from your Dashboard. This assumes you've already walked through the [Getting Started](/docs/tutorials/get-started) and [Tenzar Terminal](/docs/tutorials/tenzar-terminal) tutorials.

#### Deployment basics

A deployment is an ephemeral instance ("a server") in the cloud that you use to run your workload. When you launch a deployment on Tenzar DX, the DX Engine will do the following automatically:

1.  Spin up a Virtual Private Server (VPS) on a cloud infrastructure provider
2.  Configure compute, storage, security settings and more
3.  Transfer your Docker image and volumes to the instance
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

##### Choose your image ("environment")

You can only select one image and it cannot be changed after the deployment is launched. Your [image](/docs/images) should contain all of the frameworks, system libraries, or "environments", to run your deployment.

In this example, we want to run a Tensorflow model on a GPU instance, so we are going to select the `tensorflow-gpu` image that can be found in the DockerHub [repository](https://hub.docker.com/r/tensorflow/tensorflow/tags/) and imported as `tensorflow/tensorflow:latest-gpu` as specified by one of the image tags (i.e. "versions"). Remember that when you want to run on a GPU instance like the GC1, your image has to be built for NVIDIA GPUs with CUDA drivers and nvidia-smi. In this case, the official `tensorflow/tensorflow:latest-gpu` already comes with such GPU compatibility. You should verify that you are using a GPU compatible image by running `$ nvidia-smi` once you connect to your deployment.

> Pro tip: if you or your organization plan on frequently using the same image, you can set it as your default. Click on **Images**, select your image and choose **Set as default**.

<center>
  <img src="https://s3.amazonaws.com/assets.tenzar.com/docs/deploy--set-default.png" width="500" alt="set default"/>
</center>
<br/>

##### Choose your instance ("hardware")

For GPU deployments we have two instance types to select from: GC1 and GC8. Since we don't need all of the resources from the GC8 for this example, we will use the GC1 instance.

##### Choose your volumes ("data")

In the volumes field, we can specify all of the volumes we want to add to the deployment. For example, we are adding the Tensorflow models folder from [Github](https://github.com/tensorflow/models) (you can click 'download ZIP' to get the URL to import it directly into DX) and an image recognition dataset from the [Caltech Vision webpage](http://www.vision.caltech.edu/Image_Datasets/Caltech101/) that you can also import or upload to DX. We are also including a folder of images that I uploaded through the Tenzar Terminal.

These volumes will be automatically added to my deployment when it is launched.

##### Name your deployment

When we have multiple deployments running across our account, it's helpful to keep track of which is which. So the name option is a way to label your deployment and reference it in the Tenzar Terminal commands, for example:

```text
$ tt connect image-rec
```

Usually, if you are launching only one deployment, you can skip the name.

> Pro tip: If you destroy this deployment and start another one with the same name, this command will reference the new deployment. This allows us to write scripts to control deployments or re-use the terminal history to run the same things again.

##### Adding extra disk pace

Every deployment comes with a default 20 GB of free disk space. For example, if our image is 5 GB and our volumes total 30 GB, the deployment will start with 55 GB of disk space (30 volumes + 5 image + 20 free), 20 GB of which will be free disk space.

If we need more than 20 GB of free disk space, we can enter add it under the 'Extra Space' field. In this case we will have a total of 170 GB free - 150 GB 'extra'.

##### Ready to launch

Once we click 'Deploy', the preview will confirm the details of our deployment. Use this screen to make sure your instance type, image, and volumes are correct.

'Total Data Size' denotes the total size of the images and volumes we're adding to the deployment.

Finally, 'Approximate setup time' is our estimate for how long it will take your deployment to launch. It's a depends on the type of instance we choose and the quantity of data we add to the instance (e.g. A 100 GB will take approximately 20 minutes to deploy).

<center>
  <img src="https://s3.amazonaws.com/assets.tenzar.com/docs/deploy--preview-launch.png" width="300" alt="preview deployment"/>
</center>
<br/>

##### Monitor the Deployment

Once we click 'Deploy' on the preview pane, we'll be taken to the Deployments page. We can also see this information in the Tenzar Terminal by typing `tt monitor`.

<center>
  <img src="https://s3.amazonaws.com/assets.tenzar.com/docs/deploy--deployments.png" width="500" alt="deployments"/>
</center>
<br/>

This page will monitor the progress of your deployment. It automatically refreshes so you can keep the page open and watch the status. `Pending` means we're spinning up an instance, `Creating` means we're transferring the data and configuring the Docker container, and finally `Running` means the deployment is ready for use.

Clicking on the deployment in this window will bring up some information about it. 'Cost' updates in real time and will tell you the total cost of the deployment for the time it's been running.

<center>
  <img src="https://s3.amazonaws.com/assets.tenzar.com/docs/deploy--deployments-sidebar.png" width="150" alt="sidebar"/>
</center>
<br/>

##### Connect to your deployment

Once your deployment is in the `Running` state, we can connect to it from the Tenzar Terminal. Because we have a name for the deployment we can connect to it in three ways:

`tt connect` if this is your only running deployment

`tt connect 5aa` to using the unique deployment ID

`tt connect image-rec` using the deployment name

Once we connect, we can run our workload, see our volumes under the `/tenzar_volumes` directory, and more -- These functionalities are covered in the Tenzar Terminal tutorial.

##### Destroy when you are done

When we're done with the deployment, click 'Destroy' on the Dashboard to terminate your deployment (you'll be prompted to confirm first). You will no longer be charged for a deployment once you destroy it.

> Pro tip: Deployments are meant to be ephemeral: use them only for as long as you need them and destroy them. You can save any files from the deployment back to DX with the `tt save` command. Saving enables you to persist your files out of your instance and back to DX. You can always re-launch the same deployments.

<center>
  <img src="https://s3.amazonaws.com/assets.tenzar.com/docs/deploy--destroy.png" width="500" alt="destroy deployment/>
</center>
<br/>

You can destroy a deployment from the terminal as well:

```text
$ tt destroy image-rec
```
