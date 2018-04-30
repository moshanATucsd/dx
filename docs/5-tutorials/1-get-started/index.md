### Get Started

You can use Tenzar DX through the Web Dashboard and the Tenzar Terminal command line interface. For this tutorial, we will use the Dashboard to deploy your first instance.

##### In this tutorial you will learn how to:

1.  Navigate the Dashboard
2.  Import a file from the internet
3.  Import a public Docker image, and
4.  Launch and destroy instance

#### Log in to your account

Go to [dx.tenzar.com](https://dx.tenzar.com) or click on the top right Dashboard link to log in.

Login with your account ID, username, and password.

##### Import a file from the internet

Volumes are the files and folders you upload or import to DX. Let's say you'd like to import a small dataset from the [UCI](http://archive.ics.uci.edu/ml/index.php) Machine Learning repository that is available at: http://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data

To import this file from the internet into your volumes, go to **Console** > **Import**, select **As Volume** and paste the URL.

<center>
  <img src="https://s3.amazonaws.com/assets.tenzar.com/docs/tutorial-import-url.png" width="550" alt="import from url"/>
</center>
<br/>

Then give your volume a name like `iris-data` (remember that volume names can't contain spaces) and click import.

You will see that the file has now been imported and added to your volumes.

##### Import from Docker

In order to deploy an instance, which is nothing more than a bare bones server, you need an environment. DX uses Docker images as environments. Let's say you'd like to import a simple Linux Ubuntu Docker image from [DockerHub](https://hub.docker.com/explore/).

To import the [Ubuntu image](https://hub.docker.com/_/ubuntu/), go to **Console** > **Import**, select **As Image** and type `ubuntu`.

<center>
  <img src="https://s3.amazonaws.com/assets.tenzar.com/docs/tutorial-dockerhub-ubuntu.png" width="500" alt="DockerHub Tenzar"/>
</center>
<br/>

Of course, you are able to import any other public Docker image.

#### Launch an instance

Once you have an image and some volumes, you can launch your instance.

For this example, you will launch an E1 instance. To deploy it, go to **Console** > **Deploy**, and select the Docker image you imported, choose a lightweight `Entry E1` instance, and then add your `iris-data` data to it:

<center>
  <img src="https://s3.amazonaws.com/assets.tenzar.com/docs/tutorial-deploy.png" width="500" alt="launch deployment"/>
</center>

<br/>
<br/>

<center>
  <img src="https://s3.amazonaws.com/assets.tenzar.com/docs/tutorial-preview-deploy.png" width="300" alt="preview deployment"/>
</center>
<br/>

Click deploy to launch your instance!

> This tutorial will consume about 6 minutes of your 1,000 Free Tier computing minutes. Don't forget to stop and destroy your instance.

Launching an instance takes about five minutes as it boots up a dedicated instance, prepares your environment, and adds your data. When it's ready for use, its status will show to `Running`

<img src="https://s3.amazonaws.com/assets.tenzar.com/docs/instance-running-status.png" width="100" alt="running instance"/>
<br/>

#### Destroying your instance

Now that you've seen how easy it is to launch an instance with data and a computing environment, you can destroy it.

<center>
  <img src="https://s3.amazonaws.com/assets.tenzar.com/docs/instance-destroy.png" width="500" alt="destroy instance"/>
</center>
<br/>

Usually before destroying an instance, we would have connected, and ran a workload a few times, and then destroyed it. However, connecting to your instance requires the Tenzar Terminal and is part of [tutorial](/docs/tutorial/tenzar-terminal).
