### High Availability

Must have multiple control planes i.e. multiple master nodes. Load Balance will communicate between multiple Control Planes. Worker Nodes will also communicate to master throught Load Balancer.

#### Etcd

#### Stack Etcd
- In stacked etcd each master node will have their own control plane and their components and have their own etcd database.

#### External
- In external etcd, we remove the etcd from master nodes and we will create seperate database and we will need to create seperate server and configuration.

Most popular is Stacked Etcd.


