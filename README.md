> # KUBERNETES TUTORIAL

> **Topics Covered**

1.  **Core Concept**: 
    1.  Monolith vs Microservices
    2.  Kubernetes Architecture
    3.  Setup on local / AWS EC2
    4.  Kubectl
    5.  Annotations
2.  **Workloadt**:
    1.  Deployments
    2.  Statefulsets
    3.  Daemonsets
    4.  Replicasets
    5.  Jobs
    6.  Cronjobs
3.  **Networking**:
    1.  Cluster Networking
    2.  Services
    3.  Ingress
    4.  Network Policies
4.  **Storage**:
    1.  Persistent Volume(PV)
    2.  Persistent Volume Claim (PVC)
    3.  Storage Classes
    4.  ConfigMaps
    5.  Secrets
5.  **Scaling and Scheduling**:
    1.  HPA
    2.  VPA
    3.  Node Affinity
    4.  Taints/ Tolerations
    5.  Resource Quotes
    6.  Limits
    7.  Probes

---

> ## _**Core concepts**_

_**2\. Kubernetes Architecture**_

![]()

1.  **Kubernetes Core Components**
    1.  API Server
        *   Acts as the central management hub for Kubernetes.
        *   Exposes the Kubernetes API, which users, tools (like `kubectl`), and internal components use to communicate.
        *   Ensures that all requests are authenticated and authorized before processing.
    2.  ETCD
        *   A distributed key-value store used to persist all cluster data.
        *   Stores configuration, state, and metadata of the cluster, ensuring high availability and consistency.
        *   Plays a crucial role in maintaining the desired state of the cluster.
    3.  Scheduler
        *   Assigns workloads (pods) to specific nodes based on resource availability and constraints.
        *   Ensures efficient utilization of cluster resources.
    4.  Controller Manager
        *   Runs control loops that manage state in the cluster.
        *   Includes controllers for:
            *   Node management.
            *   Pod replication.
            *   Service endpoint updates.
            *   Job completion tracking.
2.  **Node Components**
    1.  Kubelet
        *   An agent that runs on each node in the cluster.
        *   Ensures that containers specified in pod definitions are running and healthy.
        *   Communicates with the API Server to receive workload instructions.
    2.  Service Proxy
        *   Facilitates communication between pods and services.
        *   Implements network routing rules to distribute traffic to the appropriate pods.
        *   Can work with CNI plugins (like Weave Net, Calico) to manage network connectivity.
3.  **CNI Network**
    1.  **Container Network Interface (CNI):** Provides the networking layer for Kubernetes clusters
    2.  Examples include Weave Net, Calico, and Flannel.
    3.  Ensures seamless communication between nodes and pods.
4.  **Interection Flow**
    1.  User Interection
        *   Users interact with the cluster using the `kubectl` CLI or other Kubernetes tools.
        *   Requests are sent to the **API Server**.
    2.  Internal Communication
        *   The **API Server** coordinates with **ETCD**, **Scheduler**, and **Controller Manager** to enforce the desired state of the cluster.
        *   Nodes communicate with the **API Server** via **Kubelet**.
    3.  Networking
        *   CNI plugins handle networking, ensuring pods on different nodes can communicate effectively.
5.  **Node and Pod Management**
    1.  Nodes host pods (smallest deployable units) and their containers.
    2.  The **Kubelet** on each node ensures pods are running as expected.
    3.  The **Service Proxy** directs traffic to the correct pods using networking rules.

**This architecture ensures Kubernetes can efficiently manage and scale containerized applications while providing fault tolerance and high availability.**
