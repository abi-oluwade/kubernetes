# Kubernetes

Kubernetes focuses on running thousands of containers within a production environment.

A cluster consist of at least ONE cluster master and multiple worker machines (aka Nodes)
These master and nodes run the Kubernetes cluster orchestration system.

Nametags
- Kubernetes uses labels as "nametags" and can be used to indicate roles, stability or other attributes.

Pods
A pod represents a runnable unit of work, Kubernetes takes on the work of connecting a pod to the network and the rest of the Kubernetes environment.
- "Pods" can hold any number of containers but usually only holds 2.
- A pod is connected via an overlay network to the rest of the environment

Replication Controllers
Replication controllers provide a method for managing an arbitrary number of pods. A replication controller contains a pod template, which can be replicated any number of times. Through the replication controller, K8 will manage the pods lifecycle, including scaling up and down, rolling deployments and monitoring.
- Have a pod template for creating any number of pod copies.
- Provide logic for scaling the pod up or down
- Can be used for rolling deploys.

Services
A service tells the rest of the K8 environment (including other pods and replication controllers) what services your application provides. While pods come and go, the service IP addresses and ports remain the same. Other applications can find your service through Kurbernetes service discovery
- Provide discovery
- Provide load balancing
- Provide Stable service address
- Persistent
- Find pods by label selector

Volume
A volume represents a location where containers can access and store information. The volume appears as part of the local filesystem. Volumes may be backed by local storage, Ceph, Gluster, Elastic Block Storage, or a number of other storage backends.
- Pods can mount volumes like filesystems
- Providers expose both persistent and ephemeral storage (EBS, Ceph ...)

Namespaces
A namespace functions as a grouping mechanism inside of Kubernetes. Services, pods, replication controllers, and volumes can easily cooperate within a namespace, and the namespace provides a degree of isolation from other parts of the cluster.
