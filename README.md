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

![]([https://lh3.googleusercontent.com/fife/ALs6j_E4l-3_uNJ3TqAuoSdDppiDKj55GH7KqqTGp3usCvjHjUXsc1R2wCM9Ys2u4THfwwmzf1g4pTxorsfQ6-ypE-qYl7bgnRlnp49YQ5NY4goRF2-4i8dqqzgLRBqeKdKXFgtns5JBsGrX9KejHES4DtNfQukHunSyX7WI-znVZigeFTygMnxJwWuXcFSfPEIShcT2du-FwCeIXpSKQHxVuvgB8ylTSmhtIQiSedVLwU7gmYJEpvOlerBOnuL8ncwby2WEtjVtc0uzVCkmj8qRTG3CT5ZgnOrGPBpcopOg8dtYyjMP5siAxTNfNqmaBTcuRz75uyPEorVyA7edehimRdR7MXoOSo5hUqAwkI6VPn9c927A_8aqEvY8AfT2hOZT_w6IzwQqVLFKphpP7ymFqIG4IefzP5_Av9DogZrczNrvSBE374jfYbRw8FIEhYvPaLHoURwS-hfATEdGMO7pq6X5EsQu7J2Y81MzfzfNh9zf3y1OMCKpeV6e42sgaKLNo7ESh9FtRiot069z_ncHgNPT0A61PKQ41dOThabxBrFwqUJC6JxmlgMut1rN2XK349fQzaouzFPvDsNgRtz-3uBkETpIGfh-80JDEDmxwtwkPqzbJfbu7_0HLyS3Q7Vmifv0tlGstzYUfdUZHpCUms76JXAZ0iLVtOiI_3S_p2KKNFJNxuN9mxTkZD_ixdX0RGHMmMctL3NVdxDzwhO-rxy8Kb36pGZE0uh1rclr31sUTpS8JfhkiYDpFarohs_pqdghx0L-5bGqUq1HsTV_CPRSRNn12k2G6sLjZhYykse9-k5hzZAq8Od4s7YVlPeqrwAHX9kE_3IaFgNXucHXZOPvioNl2jjzgSeZ_kaMfAUSkaTo-l7sAxfT8PPa0PnymmxknpUsV7B4H6c0ujfANNrJE-0bj9D7uWUVDl3fI6zSVyss0aCs5Fdb8BxVb2Z1wUrAQ5shrhazrZHiIDD5geGcli3tyfWlPlZR1BfMlHRcwhvoNsJ57StQgRJkdJhr6cy017PM_oY2ncX5_vGL8iGO8tK724-tNalHcVOBWwbUZiYsLrBARJNfK4u1v4-xU27VDbgMM-A8Gv3lpGS_YLV3uApNsaWIwirOSD0IV6aV0LO9_aqZS00a4H-_VK2F7IWa5AaqZkqoCGiksbFc0ZJj1c85OjOFEn69uZTL4KNhxczQ99CVlZuyRWp5K-woS8oCquHH49eZy7oFy0MhD0m1HXMYtAoIF_Rg24XYxGUq-f8cDkTwLANnAMWIMTmOtzt2TDvYzdkEDbNbW41awasX7jF8NNuGrv9udXDc9nv2AUQEeUTJjnpdo3Vty-P3h8n7ZKVycUxyZPFT4UDbqbNbflxLNgVoZHId-WEo3lJEIL1PxWjEVow_7sDTTvo60KYiuW_N7JuGOxCkqmoaMr-LDDc_Ij3R5l1j3MbTo8pRmPIxSRLQGgPaRmRyT1hYjCJ_vmJuXgiSKjXeI9h2tnyPeyBqKVTaSyirOHImPBgxihIUQjLl5yS7EfRZ_7K2pvxX8_AQm8lRxq1uS5A85xD6YZzTvXJTSOTye8dFsXsyxuvgy083HhL_6JwKJvMhMB4KiWiheMIjB9okw4GHFyUfeEuYQwkPCRH81gLsk_Rd-4RQ-uhCbrZLoLvTY9PSahRJ0Y5OpyC0GAIv12f6wgiwfYc=w1446-h917](https://lh3.googleusercontent.com/fife/ALs6j_E4l-3_uNJ3TqAuoSdDppiDKj55GH7KqqTGp3usCvjHjUXsc1R2wCM9Ys2u4THfwwmzf1g4pTxorsfQ6-ypE-qYl7bgnRlnp49YQ5NY4goRF2-4i8dqqzgLRBqeKdKXFgtns5JBsGrX9KejHES4DtNfQukHunSyX7WI-znVZigeFTygMnxJwWuXcFSfPEIShcT2du-FwCeIXpSKQHxVuvgB8ylTSmhtIQiSedVLwU7gmYJEpvOlerBOnuL8ncwby2WEtjVtc0uzVCkmj8qRTG3CT5ZgnOrGPBpcopOg8dtYyjMP5siAxTNfNqmaBTcuRz75uyPEorVyA7edehimRdR7MXoOSo5hUqAwkI6VPn9c927A_8aqEvY8AfT2hOZT_w6IzwQqVLFKphpP7ymFqIG4IefzP5_Av9DogZrczNrvSBE374jfYbRw8FIEhYvPaLHoURwS-hfATEdGMO7pq6X5EsQu7J2Y81MzfzfNh9zf3y1OMCKpeV6e42sgaKLNo7ESh9FtRiot069z_ncHgNPT0A61PKQ41dOThabxBrFwqUJC6JxmlgMut1rN2XK349fQzaouzFPvDsNgRtz-3uBkETpIGfh-80JDEDmxwtwkPqzbJfbu7_0HLyS3Q7Vmifv0tlGstzYUfdUZHpCUms76JXAZ0iLVtOiI_3S_p2KKNFJNxuN9mxTkZD_ixdX0RGHMmMctL3NVdxDzwhO-rxy8Kb36pGZE0uh1rclr31sUTpS8JfhkiYDpFarohs_pqdghx0L-5bGqUq1HsTV_CPRSRNn12k2G6sLjZhYykse9-k5hzZAq8Od4s7YVlPeqrwAHX9kE_3IaFgNXucHXZOPvioNl2jjzgSeZ_kaMfAUSkaTo-l7sAxfT8PPa0PnymmxknpUsV7B4H6c0ujfANNrJE-0bj9D7uWUVDl3fI6zSVyss0aCs5Fdb8BxVb2Z1wUrAQ5shrhazrZHiIDD5geGcli3tyfWlPlZR1BfMlHRcwhvoNsJ57StQgRJkdJhr6cy017PM_oY2ncX5_vGL8iGO8tK724-tNalHcVOBWwbUZiYsLrBARJNfK4u1v4-xU27VDbgMM-A8Gv3lpGS_YLV3uApNsaWIwirOSD0IV6aV0LO9_aqZS00a4H-_VK2F7IWa5AaqZkqoCGiksbFc0ZJj1c85OjOFEn69uZTL4KNhxczQ99CVlZuyRWp5K-woS8oCquHH49eZy7oFy0MhD0m1HXMYtAoIF_Rg24XYxGUq-f8cDkTwLANnAMWIMTmOtzt2TDvYzdkEDbNbW41awasX7jF8NNuGrv9udXDc9nv2AUQEeUTJjnpdo3Vty-P3h8n7ZKVycUxyZPFT4UDbqbNbflxLNgVoZHId-WEo3lJEIL1PxWjEVow_7sDTTvo60KYiuW_N7JuGOxCkqmoaMr-LDDc_Ij3R5l1j3MbTo8pRmPIxSRLQGgPaRmRyT1hYjCJ_vmJuXgiSKjXeI9h2tnyPeyBqKVTaSyirOHImPBgxihIUQjLl5yS7EfRZ_7K2pvxX8_AQm8lRxq1uS5A85xD6YZzTvXJTSOTye8dFsXsyxuvgy083HhL_6JwKJvMhMB4KiWiheMIjB9okw4GHFyUfeEuYQwkPCRH81gLsk_Rd-4RQ-uhCbrZLoLvTY9PSahRJ0Y5OpyC0GAIv12f6wgiwfYc=w1446-h917))

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
