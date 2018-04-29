### Understanding Tenzar DX

The Tenzar DX system revolves around three core concepts: **Deployments**, **Images**, and **Volumes**.

#### Deployments

All computations that you run on DX begin with launching a **Deployment**. A deployment is an ephemeral instance ("a server") running a container in the cloud that you use to run your workload. When you start your deployment, you select the type of instance, a Docker image, and any data you'd like to include. When your deployment is ready for use, you can access it through a standard terminal connection.

#### Images

An **Image** is a bundle of frameworks, libraries, and an operating system used to package any dependencies your workload requires. DX uses Docker images as the base computing environment of an instance, so that you can deploy your workload without having to configure or install libraries or dependencies. For example, the Tensorflow image comes with Python, Tensorflow, and other packages already installed, so that you can run your workload without installing any of it yourself. DX is compatible with Docker images and gives you the ability to import images directly from [DockerHub](https://hub.docker.com/explore/), the most popular image registry, or upload your own private images.

#### Volumes

**Volumes** are how data is stored on DX. A volume simply contains the files and folders you upload or import. You can share volumes with others, delete volumes you don't need, and deploy volumes to your computations. When you deploy an instance, you can specify exactly which volumes you want to include, so that your files are automatically transferred to it. Volumes are flexible enough to store everything you need to run your computations. A single volume can be up to 1 TB in size.

<center>
  <img src="https://assets.tenzar.com/docs/arch-clients-flow.png" alt="Tenzar DX" width="680" >
</center>
<hr>

[NEXT →](/docs/cli)
