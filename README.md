**Autok8s** is assignment rquire to be done with in 1 week


## Tasks requirements:


- Tasks requirements:
  - Automate the deployment of a local kubernetes cluster
  - Automate the deployment of a testnet cosmos rpc node
  - Automate the deployment of grafana and prometheus to view the resources used such as cpu / memory / disk space etc..
  - Estimated time: 3-4hours.
  - Duration: 1week.

## Cluster Description
- This version deploys a single-node cluster. If needed, it can be modified to a high-availability cluster.

|Role	|Quantity	|Description
|:-|:-|:-|
|Deployment Node	|1	|Runs ansible commands, reused as the first master node|
|etcd Nodes	|1	|Note: reused as master nodes|
|Master Nodes	|1	|A cluster with 1 master nodes|
|Node Nodes	|2	|Nodes running application workloads; machine configuration can be upgraded/increased as needed|




