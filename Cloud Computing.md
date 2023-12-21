## What is Cloud Computing ?
```
    Cloud Computing means storing and accessing the data and programs on remote servers that  are hosted on the internet instead of the computer's hard drive.
```
## Virtualization :
>> Virtualization is a technology that allows you create multiple instances of a physical computer or server. This enables 
   you to run multiple Operating System or applications on single host.

## Virtual Machine :
```
    - A virtual machine (VM) is a software-based emulation of a physical computer. It runs an operating system (OS) and behaves like a separate, independent computer within a host system.
    - Virtual machines provide a level of isolation, allowing multiple VMs to run on the same physical hardware without interfering with each other.
    - The hypervisor presents virtualized hardware to each VM, including virtual CPUs, virtual memory, virtual storage, and virtual network interfaces.
```
>> How Virtual Machine Works :
```
    Hypervisor is the key component of the virtual machine. It is a software layer that runs on top of the hardware layer and manages the virual machine.
    The Hypervisor manages resource allocation, commmunication between VMs and isolation between VMs.
```
>> Type 1 Hypervisor (Bare Metal Hypervisor)
```
    They are installed directly on the physical hardware of the host system.
    They have direct access to the hardware resources and are responsible for managing virtual machines without relying on a host operating system.
    Generally, Type 1 hypervisors are considered more efficient and have lower overhead because they operate closer to the hardware.
    Commonly used in enterprise environments for server virtualization.
    Examples : VMware ESXi, Microsoft Hyper-V Server, KVM, etc.
```
>> Type 2 Hypervisor (Hosted Hypervisor)
```
    They are installed on top of an existing operating system, just like other software applications.
    They rely on the host operating system for resource management and communication with hardware.
    Their performance is low as compared to type-1 because they are not close to hardware as comapared to type-1.
    Commonly used for developement and testing where performance is not important.
    Examples : VMware Workstation, Oracle Virtual Box, etc.
```
## IaaS, PaaS, SaaS :
```
    1. IaaS (Infrastructure as a Service):
        - What it is:

        Imagine you need a computer, but instead of buying a physical machine, you rent a virtual one.
        IaaS provides virtualized computing resources over the internet. It includes virtual machines, storage, and networking.
        
        - Example:

        You rent a virtual machine from a cloud provider (e.g., Amazon EC2, Microsoft Azure Virtual Machines) and have control over the operating system, applications, and configurations.

    2. PaaS (Platform as a Service):
        - What it is:

        Think of PaaS as providing a platform that simplifies the development and deployment of applications.
        It includes tools and services for building, testing, and hosting applications without worrying about the underlying infrastructure.

        - Example:

        You use a PaaS offering (e.g., Google App Engine, Heroku) to deploy and manage your web application. The platform takes care of the server, database, and scaling.

    3. SaaS (Software as a Service):
        - What it is:

        In the SaaS model, software applications are provided over the internet, eliminating the need for users to install, maintain, and update the software on their devices.
        
        - Example:

        Instead of buying and installing email software, you use a SaaS email service like Gmail or Microsoft 365. The service provider manages everything related to the email service.
```
## Containers :
```
    Containerization is a lightweight form of virtualization that allows you to package and isolate applications and their dependencies into a container. Containers are portable, consistent, and can run on any environment that supports the containerization platform.

    Containers do not have their own physical hardware; instead, they share the host system's kernel and resources. Containers provide a lightweight form of virtualization that allows multiple isolated environments (containers) to run on a single host machine. Each container runs as a process on the host operating system and shares the same kernel with other containers.

    Containers leverage the Linux kernel's namespaces and cgroups to provide process and resource isolation. Each container has its own isolated file system, process space, and network, but they all share the same underlying kernel of the host operating system.
```

## Docker :
```
    Docker is a open source platform that uses containerization technology.
    It allows developers to package applications and their dependencies into lightweight portable containers.
    
    C-Groups -> Control Groups allocates resources among the processes.
    NameSpaces -> namespaces restrict a containers access and visibility to other resources on the system.

    -> Docker uses cgroups to implement resource isolation for containers. When you run a container with Docker, the Docker daemon creates a cgroup for that container, allowing it to control and limit the container's access to system resources.
    -> Docker leverages namespaces to create an isolated environment for each container.
    -> Users interact with the Docker daemon using the Docker CLI (docker command). When a user runs a Docker command to
       start a container, the Docker CLI communicates with the Docker daemon, which, in turn, interacts with cgroups and namespaces to create and manage the container.
```
>> Docker Image :
   A Docker image is a lightweight, standalone, and executable package that includes all the necessary components to run a piece of software. 
   In simple language, a Docker image serves as a blueprint for creating containers.
   Docker images are built from a set of instructions called a Dockerfile.
   Docker images are immutable, meaning once an image is built, its contents cannot be changed. If modifications are required, a new image must be built.

>> Docker Container :
   A Docker container is a executable instance of a Docker image. It is an isolated environment that encapsulates an application and its dependencies, running as a process on the host system.
   Containers are designed to be stateless and immutable. Any changes made during runtime are isolated to the specific container instance. If changes are needed, a new container based on an updated image is created.  

## Architectural Approaches :

>> Monolithic Architecture :
```
    A monolithic architecture refers to an application that is built as a single, indivisible unit.
    A single codebase containing all the functionalities (product catalog, order processing, user authentication, etc.).
```

>> Microservices :
```
    Microservices architecture is an approach where an application is divided into small, independent services that communicate with each other through well-defined APIs.
    Each service in a microservices architecture is designed to perform a specific business function and can be developed, deployed, and scaled independently.
    We can take an example of e-commerce website. we can divide that application on the basis of functionalities into indivisual services.
    For Example we can make User Service which will handle user authentication, user profile related functionality. we can make Product Service which will handle product catalog, product related functionality.
    In Microservice Architecture, API Gateway serves as a central point for client interaction with the microservices.
    It routes requests to the appropriate services.
```
```
    (1) Adding a new feature to any service will be easy. In microservices architecture, a new feature can be added
        independently, without modifying other services.
    (2) If any error occurs in any of the service, it will not affect the working of other services. Faults will be isolated.
    (3) If any service experiences increased demand, then that indivisual service can be scaled independently.
    (4) Each service can be implemented using different technology as per the requirements.
```