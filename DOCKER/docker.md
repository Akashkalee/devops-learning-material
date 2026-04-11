# DOCKER

### What is Docker?
Docker is an OS-level virtualization (or containterization) platform, which allows applications to share the host OS kernel instead of running a separate guest OS like in traditional virtualization. This design makes Dokcer containers lightweight, fast, and portable, while keeping them isolated from one another.

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


