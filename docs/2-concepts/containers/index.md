### Containers

#### What are Containers
Once you understand that images are a software bundle of system libraries, system frameworks, and settings packaged as a single file, then containers are easy to understand: A container is created by running an image. That is, when you want to use an image in a computation, then your image becomes a container. This container runs on your deployed instance thereby giving you access to the underlying CPUs, memory, and GPUs of your instance. You can launch multiple instances with containers from the same image.

#### Why Containers
DX uses containers in your instances for 2 main reasons: 1) Give you the flexibility to run workloads with any frameworks and dependencies, and 2) Isolate your workload from the underlying infrastructure to provide the strongest default isolation and security.

#### Container Advantages
In contrast to a virtual machine (VM) that is harder to configure, slower to boot-up, and larger in size, containers are lightweight in size and fast to run. By supporting Docker images and containers, DX gives you immediate access to the largest collection of public images that are can be instantly deployed in DX. DX also automatically supports GPU container runtime so that you can run GPU specific images without any configuration.
