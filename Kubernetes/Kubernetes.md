# Kubernetes
Kubernetes is a container management technology developed in google lab to manage containerized applications in different kind of enviornment such as physical, virtual, and cloud infrastructure. It is an open source system which helps in creating and managing containerization of application. This tutorial provides an overview of different kind of features and functionalities of Kubernetes and teaches how to manage the containerized infrastructure and application deployement.

### What is Kubernetes?
Kubernetes is open-source contianer orchestration platform originally developed by Google and now maintained by the Cloud Native Computing Foundation (CNCF). It enables automated deployment, scaling, and management of containerized applications across cluster of machines. Kubernetes helps organizations transition from host-centric to container-centric infrastucture, improving resource utilization and operational efficiency.

**Key Features of Kubernetes**

Kubernetes comes with a robust set of features for managing modern cloud-native applications:
- **Application centric management** - Foucuses on treating applications as top priority, making it easier to configure and run them automatically.
- **Automated deployment and scaling** - Automatically adjusts workloads based on demand.
- **Auto scaling capabilities** - Supports scaling up and down based on real-time demand.
- **Containerized infrastructure** - Manages applications in containers across different machines, ensuring they are always available and portable.
- **Continuous development, integration, and deployment** - Supports automated application updates and deployments using tools like Jenkins, ArgoCD, and Tekton.
- **Environment consistency across development, testing and production** - Ensures consistent environments across different stages using simple configuration.
- **Efficient resource utilization** - Optimizes the use of CPU, memory, and storage with built-in policies.
- **Self healing and fault tolerance** - Automatically restarts failed containers and replaces unhealthy nodes to maintain stabiliy.

###  Advantages of Kubernetes

Kubernetes has many benefits that make it an important tool for managing applications in containers. Some of the main advantages are:
- Scalability − Kubernetes can automatically scale applications up or down based on demand. It can handle dynamic traffic patterns and adjust resources accordingly.
- High Availability − It ensures that your applications are always available. Kubernetes can automatically restart containers that fail, replace containers, and distribute workloads across nodes to avoid downtime.
- Load Balancing − Kubernetes has built-in load balancing to distribute traffic across containers effectively, which enhances application performance and reduces the risk of server overload.
- Self-Healing − Kubernetes automatically detects failed containers and replaces or restarts them, ensuring that the system remains healthy and applications continue to run without manual intervention.
- Portability − Kubernetes abstracts the underlying infrastructure, allowing applications to run consistently across different environments (on-premises, cloud, or hybrid).
- Cost Efficiency − Kubernetes enables better resource utilization by allowing applications to run on shared resources and scale efficiently.


### Prerequisites to Learn Kubernetes
Assuming anyone who wants to understand Kubernetes should have an understating of how the Docker works, how the Docker images are created, and how they work as a standalone unit. To reach to an advanced configuration in Kubernetes one should understand basic networking and how the protocol communication works.




## Kubernetes - Cluster Architecture

<img width="880" height="720" alt="Docker Architecture (3)" src="https://github.com/user-attachments/assets/2176846a-1058-4345-96ad-dd9cb5b2309e" />


