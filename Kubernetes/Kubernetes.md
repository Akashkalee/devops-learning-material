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

<img width="820" height="620" alt="Docker Architecture (3)" src="https://github.com/user-attachments/assets/2176846a-1058-4345-96ad-dd9cb5b2309e" />

A Kubernetes cluester consists of a control plane plus a set of worker machines, called nodes, that run containerized applications. Every cluster needs at least one worker node in order to run Pods.
The worker nodes(s) host the Pods that are the components of the the application workload. The control plane manages the worker nodes and the Pods in the cluster. In production environments, the control plane usually runs across multiple computers and a cluster usually runs multiple nodes, providing fault-tolerance and high availability.

#### Control plane components
The control plane's components make global decisions about the cluster (for example, scheduling), as well as detecting and responding to cluster events (for examples, starting up a new pod when a deployments replicas field is unsatisfied).
Control plane components can be run on any machine in the cluster. However, for simplicity, setup scripts typically start all control plane components on the same machine, and do not run user containers on this machine. 

#### kube-apiserver 
The API server is a component of the Kubernetes control plane that exposes the kubernetes API. The API server is the front end for the kubernetes control plane.
The main implementation of a Kubernetes API server is kube-apiserver. kube-apiserver is designed to scaled horizontally that is, it scales by deploying more instances. 

#### etcd
Consistent and highly-available key value store used as Kubernetes backing store for all cluster data.
If your Kubernetes cluster uses etcd as its backing store, make sure you have a back up plan for the data.

#### kube-scheduler 
Control plane component that watches for newly created Pods with no assigned node, and selects a node for them to run on.
Factors taken into account for scheduling decision include: individual and collective resource requirements, hardware/software/policy constraints, affinity and anti-affinity specifications, data locality, inter-workload interference, and deadlines.

#### kube-controller-manager 
Control plane component that runs controller processes.
Logically, each controller is a separate process, but to reduce complexity, they are all compiled into a single binary and run in a single process.
There are many different types of controllers. Some examples of them are:
- Node controller: Responsible for noticing and responding when nodes go down.
- Job controller: Watches for job objects that represent one-off tasks, then creates Pods to run those tasks to completion.
- EndpointSlice controller: Populates EndpointSlice objects (to provide a link between Services and Pods).
- ServiceAccount Controller: Create default ServiceAccounts for new namespaces.
The above is not an exhaustive list.

#### cloud-controller-manager
A Kubernetes control plane component that embeds cloud-specific control logic. The cloud controller manager lets you link your cluster into your cloud provider's API, and separates out the components that interact with that cloud platform from components that only interact with your cluster.
The cloud-controller-manager only runs controllers that are specific to your cloud provider. If you are running Kubernetes on your own premises, or in a learning environment inside your own PC, the cluster does not have a cloud controller manager.
As with the kube-controller-manager, the cloud-controller-manager combines several logically indepedent control loops into a single binary that you run as a single process. You can scale horizontally (run more than one copy) to improve performance or to help tolerate failure.

The following controllers can have cloud provider dependencies:

- Node controller: For checking the cloud provider to determine if a node has been deleted in the cloud after it stops responding
- Route controller: For setting up routes in the underlying cloud infrastructure
- Service controller: For creating, updating and deleting cloud provider load balancers


### Node components 
Node components run on every node, maintaining running pods and providing the Kubernetes runtime enviornment.

#### Kubelet 
An agent that runs on each node in the cluster. It makes sure that containers are running in a Pod.
The kubelet takes a set of PodSpecs that are provided through various mechanisms and ensures that the containers described in those PodSpecs are running and healthy. The kubelet doesn't manage containers which were not created by kubernetes.

#### kube-proxy(optional)
kube-proxy is a network proxy that runs on each node in your cluster, implementing part of the Kuberenetes Service concept.
kube-proxy maintainers network rules on nodes. These network rules allow network communication to your Pods from network sessions inside or outside of your cluster.
kube-proxy uses the operating system packet filtering layer if there is one and it's available. Otherwise, kube-proxy forwards the traffic itself.
If you use a network plugin that implements packet forwarding for Services by itself, and providing equivalent behavior to kube-proxy, then you do not need to run kube-proxy on the nodes in your cluster.

#### Container runtime 
A fundamental component that empowers Kubernetes to run containers effectively. It is responsible for managing the execution and lifecycle of containers within the Kubernetes environment.

Kubernetes supports container runtimes such as containerd, CRI-O, and any other implementation of the Kubernetes CRI (Container Runtime Interface).


