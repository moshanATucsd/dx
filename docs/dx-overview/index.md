
### Tenzar DX

#### Introduction
This guide will introduce you to the Tenzar DX platform and to the Tenzar Terminal.

> If you have any questions along the way, please refer to the documentation or contact our [phone support](https://dx.tenzar.com/support).

### Overview

The Tenzar DX platform revolves around three concepts: **Deployments**, **Images**, and **Volumes**.

All of the computations that you run on DX begin with launching a **Deployment**. A deployment is an ephemeral virtual machine instance in the cloud that you use to run any arbitrary computation through a standard terminal.

An **Image** is the base computing environment of an instance. An image is a bundle that consists of an operating system, frameworks, and any other pre-installed software. For example, a machine learning image might come with Python and Tensorflow already installed. DX is compatible with Docker images and gives you the ability to import images directly from [DockerHub](https://hub.docker.com/explore/), the most popular image registry.

**Volumes** are how data and files are stored on DX. A volume simply contains files and folders uploaded from your computer. When you deploy an instance, you can specify exactly which volumes you want to mount on your instance. A volume might contain code scripts or a large dataset. Volumes are flexible enough to store everything you need to run your computations.

<center>
  <img src="https://assets.tenzar.com/app/img-flow.png" alt="Tenzar DX" width="600" >
</center>
<hr>

[next](/docs/tenzar-terminal/index.md)
