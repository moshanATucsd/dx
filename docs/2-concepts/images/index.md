### Images

#### What are Images
An image is a lightweight, stand-alone, bundle of software that includes everything you need to run your workload: system libraries, system frameworks, packages, settings, and runtime. When you deploy an Image -- which is just a file -- it transforms into a running container on the instance. DX leverages containers to abstract all of the dependencies you need for your workload. And best of all, DX supports the industry-standard Docker images and is integrated with DockerHub.

#### Why Images
DX uses images to enable you to run any kind of computation, in any language, with any frameworks, without installing it yourself. For example, imagine that every time you started your computer you had to re-install all of your applications, system libraries, and software - you'd probably choose not to do it. That's why DX uses images: by bundling all of your dependencies into a Docker image, you can have a standard "environment" to run your workloads.


#### Images Advantages
By enabling you to store public or private Docker images in DX (i.e. an "Image Registry"), you can share images within your team or with other teams, so that they can easily run and reproduce your workloads without needing to install packages and dependencies across different machines.

When you select and image for a deployment, DX also handles the runtime of an image. What that means is that DX Engine automatically boots-up your image and runs it as container within your instance, so that you don't have to worry about troubleshooting or learning Docker. 
