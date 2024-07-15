**Autok8s** is assignment rquire to be done with in 1 week


## Tasks requirements:


- Tasks requirements:
  - Automate the deployment of a local kubernetes cluster
  - Automate the deployment of a testnet cosmos rpc node
  - Automate the deployment of grafana and prometheus to view the resources used such as cpu / memory / disk space etc..
  - Estimated time: 3-4hours.
  - Duration: 1week.

## Solution plan
- Use kubeadm kubectl kubelet
- Install promethues
- k8s-cosmos-gaia

## Cluster Description
- This version deploys a single-node cluster with kubeadmin. If needed, it can be modified to a high-availability cluster with k8s source.

|Role	|Quantity	|Description
|:-|:-|:-|
|Deployment Node	|1	|Runs ansible commands, reused as the first master node|
|etcd Nodes	|1	|Note: reused as master nodes|
|Master Nodes	|1	|A cluster with 1 master nodes|
|Node Nodes	|2	|Nodes running application workloads; machine configuration can be upgraded/increased as needed|



## How to use it

- Prepare your running env. Now we setup with 1 master node and 2 worker nodes.
- Set up passwordless SSH login

`$ sudo ssh-copy-id $IP `

- Git clone this repo on master node. It also used as ansible runner.

`$ git clone https://github.com/terrydevops/autok8s.git`

- Install Ansible

`$ sudo apt update`

`$ sudo apt-get install ansible`

`$ cd ./autok8s`

- Change the IP list in inventories/group_vars/all.yml


`sudo ansible-playbook playbooks/setup_kubernetes.yml`


## Todo list

- Run ansible with runner 
- Timezone Sync (chrony)
- Test cases
- Support HA with master node
- Support HA with etcd
- Support different network: calico, cilium, flannel, kube-ovn, kube-router
- Upgrade/remove support
- Build k8s from source code
- Other requirements(kubernetes-sigs/metrics-server load-balancer docker runtime )






  




