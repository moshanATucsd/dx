### Containers

When you use an image in a computation, a container is created. This container runs on your deployed instance and gives you access to the underlying CPUs, memory, and GPUs. You can launch multiple instances with containers from the same image.

#### Why Containers?
DX uses containers in your instances for 2 main reasons: 

1) To give you the flexibility to run workloads with any frameworks and dependencies.
2) To isolate your workload from the underlying infrastructure to provide the strongest default isolation and security.

#### Container Advantages
In contrast to a virtual machine (VM) that is harder to configure, slower to boot-up, and larger in size, containers are lightweight in size and fast to run. By supporting Docker images and containers, DX gives you immediate access to the largest collection of public images in the world. DX also supports GPU container runtime so that you can run GPU-specific images without any configuration.
