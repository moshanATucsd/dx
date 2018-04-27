### Instances

#### What are Instances
An instance is a blank-slate server ("machine") used by DX to deploy and run your workloads. DX supports various instance types comprised of varying combinations of CPU, memory, GPUs, disk space, and networking capacity to give you the flexibility to choose the appropriate mix of computing resources for your workloads. 

#### Why Instances
DX runs your workloads in independent and dedicated instances that give you 100% of the computing resources. When you deploy an instance, DX automatically creates the instance for you, installs a *copy* of your selected Docker image, and *copies* any selected volumes into it. Instances take approximately 5-minutes to prepare, as DX must start a blank-slate server, load it with your image, run your container, transfer your volumes, and then provide you with access.

DX treats instances as transactional processes: DX launches your instance, you run your workload, and then you delete the instance. Unlike traditional servers that are designed to run 24/7 - and lead to an increase in costs - DX instances are meant to be used only for the duration of your workload. Once you are done using an instance, you delete it. This transactional nature makes instances "ephemeral" (i.e. used only once and discarded).

You can always re-launch identical instances with the same configurations, image, and volumes from the Tenzar Terminal or Dashboard. Remember that an instance only contains a *copy* of your image and volumes. So when you delete an instance, you can always re-use your volumes and images from DX. Additionally, any new files or folders created within the instance can be saved to DX via the Tenzar Terminal's `tt save` command.


#### Instances Advantages
DX utilizes powerful server instances operated by cloud providers like Amazon Web Services to run your workloads. By automating the deployment, boot-up, data-transfer, security, and runtime, DX makes it possible to easily run workloads ephemerally and only for the necessary duration. Streamlining this process reduces computing time costs and saves you from spending time with configurations and installations.

Since instances are isolated and independent from each other, you can launch and run up to 64 concurrent instances with the same or different computation without slowing down or consuming resources from other instances. The ability to automate and deploy workloads with 1-click seriously accelerates the development cycle across your team.

Additionally, through the DX Compute Engine, you are able to automatically run complex and  automated workflows of any size, without having to manually execute each command yourself.
