<h1 class="title">$ tt deploy [parameters] [volume(s)]</h1>

#### Description
Launches a virtual machine instance with the specified parameters, such as volume(s), image, instance type, and extra storage.

Deployments take a few minutes to launch depending on the size of image, volume(s), and type of instance. You can check the status of the deployment with `tt monitor`. You are allowed to connect to the instance once its status is `Running`.

Using `tt deploy` without any parameters uses the default deployment configuration (you can favorite an image for your organization from the images dashboard). To launch an instance with your volume(s), image, and additional settings, you must specify them in the parameters. Before launching, you will see the summary of the deployment, with the option to cancel it or continue.

Deployments are ephemeral. By 'ephemeral' we mean that the mounted volumes, memory, active processes, etc., within the instances are wiped when it's destroyed. Destroying a deployment does not delete the actual image or volume(s) stored in DX — only the copy used in the deployment. In order to save files that you do not want destroyed use `tt save` or `tt get`.

#### Parameters
| Flag, Name | Description | Required |
|---------|-------------|-------------|
| `-i, --image` | Image to use in deployment. | - |
| `-t, --type` | [Instance type](https://dx.tenzar.com/computing) to use in deployment.| - |
| `-s, --space` |	Amount of additional disk space in GiBs. Every deployment comes with 20 GiB of free disk space. |	- |
| `-n, --name` |	Names the deployment.| - |
| `volume(s)` | Volume(s) to use in deployment.| - |


#### Usage
```text
tt deploy
# or
tt deploy myVolume
# or
tt deploy -i myImage -t c1 myVolume
# or
tt deploy -i myImage -t c1 myVolume myVolume2 -n deploymentName
# or
tt deploy --image myImage --type c1 --name deploymentName myVolume myVolume2
```

#### Note
Deploying an instance creates a secure, private, virtual instance in the cloud to run your programs. You pay as you go for the amount of time you have an instance `Running`. Compute billing is calculated from the time you click `ENTER` to deploy, until you `tt destroy` your deployment. To avoid unnecessary charges, destroy your deployments when you are done using them.
