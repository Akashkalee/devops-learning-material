# DOCKER

### What is Docker?
Docker is the open platform for developing, shipping, and running application. Docker enables you to separate your application from your infrastructure so you can deliver software quickly. With Docker, you can manage your infrastructure in the same ways you manage your applications. By taking advantage of Docker's methodologies for shipping, testing, and deploying code, you can significantly reduce the delay between writing code and running it in production.

### Before Docker
Before Docker, deploying applications across different environments was a nightmare. Differences in dependencies, library versions, and OS configurations led to the infamous "works on my machine" problem.

### Docker's Solution:
Docker solves this by standardizing the runtime environment. By bundling the application code with its specific dependencies into a single unit, it ensures the software runs identically whether it's on a developer's laptop, a test server, or a cloud cluster.
- Portability: Runs anywhere in local machine, cloud, on-prem servers.
- Consistency: Same behavior in development, testing, and production.
- Lightweight: No full OS per app; containers share the host kernel.
- Scalability: Ideal for microservices and orchestrators like Kuberenetes and Docker Swarm.
- Efficiency: Starts in seconds, uses fewer system resources.


### Docker Architecture:

![Docker Architecture (2)](https://github.com/user-attachments/assets/03fbdf0c-22ab-45d4-915b-37ce32bbb9f5)

Docker uses a client-server architecture. The Docker client talks to the Docker daemon, which does the heavy lifting of building, running, and distributing your Docker containers. The Docker client and daemon can run on the same system, or you can connect a Docker client to a remote Docker daemon. The Docker client and daemon communicate using a REST API, over UNIX sockets or a network interface. Another Docker client is Docker Compose, that lets you work with application consisting of a set of containers.

### The Docker daemon
The Docker daemon (dockerd) listens for Docker API requests and manages Docker objects such as images, containers, networks, and volumes. A daemon can also communicate with other daemon to manage Docker services.

### The Docker client
The Docker client(docker) is the primary way that many Docker users interact with Docker. When you use commands such as docker run, the client sends these commands to dockerd, which carries them out. The docker command uses the Docker API. The Docker client can communicate with more than one daemon.

### Docker registries
A Docker registry stores Docker images. Docker Hub is a public registry that anyone can use, and Docker looks for images on Docker Hub by default. You can even run your own private registry.
When you use the docker pull or docker run commands, Docker pulls the required images from your configured registry. When you use the docker push command, Docker pushes your image to your configured registry.

### Docker objects
When you use Docker, you are creating and using images, containers, networks, volumes, plugins and other objects. This section is a brief overview of some of those objects.

#### Images
An image is a read-only template with instructions for creating a Docker container. Often, an image is based on another image, with some additional customization. For example, you may build an image that is based on the Ubuntu image but includes the Apache web server and your application, as well as the configuration details needed to make your application run.
You might create your own images or you might only use those created by others and published in a registry. To build your own image, you create a Dockerfile with a simple syntax for defining the steps needed to create the image and run it. Each instruction in a Dockerfile creates a layer in the image. When you change the Dockerfile and rebuild the image, only those layers which have changed are rebuild. This is part of what makes images so lightweight, small, and fast, when compared to other virtualization Technologies.

Containers
A container is a runnable instance of an image. You can create, start, stop, move, or delete a container using the Docker API or CLI. You can connect a container to one or more netwroks, attachh storage to it, or even create a new image based on its current state.
By default, a container is relatively well isolated from other conatiners and its host machine. You can control how isolated a conatiner's network, storage, or other underlying subsystems are from other containers or from the host machine.
A container is defined by its image as well as any configuration options you provide to it when you create or start it. When a container is removed, any changes to its state that aren't stored in persistent storage disappear.

### What is Docker Engine?

Docker Engine is the actual technology behind building, shipping, and running container applications. However, it does its work in a client-server model, which requires using many components and services for such operations. When people refer to "Docker" they are probably referring to either Docker Engine itself or Docker Inc, the company that provides several versions of containerization technology based on Docker Engine.

### Components of Docker Engine
Docker Engine is an open-source technology that includes a server running a background process called a REST API, and a command-line interface(CLI) known as 'docker'. 
How it runs?
It runs a server-side daemon that manages images, containers, networks, adn storage volumes. The users can interact with this daemon with the help of the CLI, directly through the API.
As essential aspect of Docker Engine is its declaraive nature. This means that administrators describe a specific desired state for the system. Docker Engine automatically works at keeping the real state aligned with the desired state at all time.


