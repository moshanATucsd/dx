### Usage 101: Tenzar Terminal

<i>The following tutorial teaches you how to use the Tenzar Terminal on macOS or Linux computers. Click [here](https://dx.tenzar.com) to download and install Tenzar Terminal.</i>

This 101 guide will walk through the basic end-to-end usage of the Tenzar Terminal using a computer vision example in the context of self driving cars.

All commands in the Tenzar Terminal have the following structure:

<img src="https://assets.tenzar.com/app/img-commands.png" alt="Command" width="100%" style="border-radius: 3px; padding-bottom: 20px">

- Angle brackets `< >` indicate required parameters.
- Square brackets `[ ]` indicate optional parameters.
- Single dash `-` indicates shorthand options.
- Double dashes `--` indicate long form options.


#### Login

To begin using the Tenzar Terminal, log into your organization with your username and password.

```bash
$ tt login

Organization ID: octo-org
Username: octo
Password:
Login successful.
```

Once you are authenticated, you can begin using the Tenzar Terminal.

Deployments in DX launch with images you upload or import from DockerHub. If you use the same image frequently, you can set it as your default from your images panel.

In this demo we use a custom image that comes preinstalled with a number of packages, including OpenCV, Tensorflow, and others. To import this image into DX, run:

```bash
$ tt import tenzardockerhub/tutorial:selfdriving --name tenzar-tutorial
```

This imports the DockerHub image with the name 'tenzar-tutorial' into your account. Note that while you are importing an image from the [tenzardockerhub](https://hub.docker.com/r/tenzardockerhub) public account in this example, you are also able to import any other public image from any other DockerHub account. Since imports take a few minutes, in the meantime, let's take a look at volumes.


#### Volumes

To follow along, download the following examples files and put them in your Desktop:
- [selfdriving.zip](https://assets.tenzar.com/app/selfdriving.zip): a Python program for performing car lane detection.
- [video.mp4](https://assets.tenzar.com/app/video.mp4): a sample driving footage that we will as our data to run the model on.

Feel free to watch the video to get a feel of what we are going to be working with.

To upload the selfdriving code as a DX volume run:

```bash
$ tt upload ~/Desktop/selfdriving

Uploading 'selfdriving' as volume 'selfdriving'.
/ [████████████████████████████████████████████]
  6.78 MiB/6.78 MiB                   2.88 MiB/s
Upload complete.
```

Now upload the video in the same way:

```bash
$ tt upload ~/Desktop/video.mp4

Uploading 'video.mp4' as volume 'video.mp4'.
/ [████████████████████████████████████████████]
  14.39 MiB/14.39 MiB                 3.01 MiB/s
Upload complete.
```

You should now be able to view your uploaded volumes:

```bash
$ tt volumes

         VOLUME         |    CREATED     |   SIZE
+-----------------------+----------------+-----------+
  selfdriving           | 2 minutes ago  | 6.78 MiB
  video.mp4             | 1 minute ago   | 14.39 MiB
```


#### Deploy

By now, your import of the tenzar-tutorial image should be complete. To view your images and pending imports, run:

```bash
$ tt images

         IMAGE        |    CREATED     |   SIZE
+---------------------+----------------+-----------+
  tenzar-tutorial     | 5 minutes ago  | 2.78 GiB
```

If the image is still importing, just check back in a couple of minutes.

Now that the image, your code, and your data are on DX, you are ready to start a deployment. For this demo, we are going to use the following command:

```bash
$ tt deploy --image tenzar-tutorial --type e1 video.mp4 selfdriving
```

This will deploy an E1 [instance of type](/computing) with the image `tenzar-tutorial` and the `video.mp4` file and `selfdriving` folder as volumes. You can check the status of your deployment with:

```bash
$ tt monitor

  DEPLOYMENT ID |   CREATED     |      IMAGE      | TYPE |    STATUS
+---------------+---------------+-----------------+------+-------------------+
  78a8675cb3e9  | 6 seconds ago | tenzar-tutorial | E1   | Pending (1/2)
```

During this process, your image and volume(s) are being initialized and copied onto the instance for use. Check back in 5 - 10 minutes and your deployment should be up and running. Note: the time needed to boot-up the deployment depends on the size of your volume(s) and type of instance.


#### Connect

Once your deployment is in the `Running` state, you are ready to connect to it using its ID. Run the following command, making sure to replace the ID with what's listed under your `tt monitor` command (or just the first unique characters).

```bash
$ tt connect 78a8675cb3e9
```

This starts a terminal SSH session inside your deployed instance. That means you are ready to run your code!

You can find the volumes that you added to the deployment under the `/tenzar_volumes` directory.

```bash
root@78a8675cb3e9:/ cd /tenzar_volumes/
```
**Hint:** you are connected to an instance when your terminal prompt begins with `root@`.

The program we want to run is located in the `selfdriving` directory. To execute this specific code, we pass in the sample video footage as an input file and an output file to see the results:

```bash
root@cc99b263ea7f:/ python selfdriving/pipeline.py video.mp4 results.mp4
```
This starts the computer vision model, which takes a few seconds to run. When it completes, it creates the results.mp4 file within the same directory.


#### Save

You can now save a copy of this file back to DX. To do so, exit your current instance session by typing exit, which closes your connection but leaves the instance running, and then save this file with:

```bash
$ tt save 78a8675cb3e9 results.mp4
```

When the save completes, you can see this file saved in your volumes:

```bash
$ tt volumes

         VOLUME         |    CREATED     |   SIZE
+-----------------------+----------------+-----------+
  selfdriving           | 8 minutes ago  | 6.78 MiB
  video.mp4             | 8 minutes ago  | 14.39 MiB
  results.mp4           | 7 seconds ago  | 14.36 MiB
```


#### Download

You can download this volume to your computer with:

```bash
$ tt download results.mp4
```

By default, the results.mp4 file is downloaded into your Downloads folder.

You can now open the video and see the results of the lane finding program.


#### Destroy

When you are finished with your computations, destroy your deployment:

```bash
$ tt destroy 78a8675cb3e9
```

Deployments are meant to be temporary or ("*ephemeral*"): Once you are done using them, you save the data you need, and then you destroy them. You can easily relaunch and reproduce your deployment at any time.


#### Conclusion

You've now been introduced to the core concepts of Tenzar DX. We have a team that is able to provide support and guidance to your organization with your next steps — whether that is migrating existing data to DX, installing DX across your organization, training other users, scaling your computations, creating custom computing environments, or deploying complex workflows, we can help. Just [reach out](/sales).
