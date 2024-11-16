## Architecture

Kubernetes architecture is master - slave architecture, and slave is referred to as workers often.

Master Node: 
Mater node is responsible for cluster management and its entry point for overall administrative tasks. There can be a single Master node and in HA mode there could be more than one Master nodes. Hence Multi Master Architecture is supported by Kubernetees.

![alt text](./imgs/img01.jpg)

Above diagram depicts a high level architecture of the kubernetes architecture.

The end user can submit the request to k8-cluster either by CLI or using API's or K8 UI dashboard which will be entertained by the Master node. The master node has multiple components like scheduler, api-Server, key-value pair store (etcd), contoller and combination is called the control plane. 

There can be multiple worker nodes which can connect to one or more master nodes. And the worker nodes has kube-proxy, pods and services.

### Master Node

#### Api Server
Also known as Kube-api-Server is the the entry point for all the rest commands used to control the cluster.

#### Etcd
Its a distrubuted key-value store to store the cluster state. It's role in crucial in getting high availability as it helps during leader selection and cluster management.

#### Scheduler
Kube Scheduler is the component which regulates the tasks on slave nodes. Stores the resource usage information for each slave node.

#### Controller
Runs multiple Controller utility in single process. It is responsible for carrying out automated taks in K8 cluster. It is responsible for executing jobs as there will be lots of automated tasks which cluster can execute and all tht particular thing is done by the cube control manager or cube controller.

### Worker Node.
Worker nodes are physical or vm's where the container are managed by the master node. They contain all the necessary services to manage the networking between the containers, communicate with the master node, and assign resources to schedule containers.

Ecach worker node has kubelet, which is a k8 agent on worker nodes. It will communicate with the master node's cube-APi and follow instructions as intructed by master node. Kubelet gets the configuration of pod from the api server and ensures that the described containers are up and running.

#### Pods
Its a group of one or more containers with shared storage/network and sepcification for how to run the containers. We must have all the containers which are running in a single pod must have similar kind of configuration and we cannot execute cross configuration containers within a single pod.
Pods share the same shared content and same ip but reach other pods via localhost and IP is not associated with containers.
Single pod can run on multiple multiple machnes or single machine can run multiple pods.

#### kube-proxy
kube-proxy runs on each node to deal with individual host sub-netting and ensure that the services are available to external parties.

