**Autok8s** is assignment rquire to be done with in 1 week


## Tasks requirements:


- Tasks requirements:
  - Automate the deployment of a local kubernetes cluster
  - Automate the deployment of a testnet cosmos rpc node
  - Automate the deployment of grafana and prometheus to view the resources used such as cpu / memory / disk space etc..
  - Estimated time: 3-4hours.
  - Duration: 1week.

## Solution plan
- Use kubelet=1.28.2-1.1 - kubeadm=1.28.2-1.1 - kubectl=1.28.2-1.1 and Ubuntu22.04
- Install promethues
- [k8s-cosmos-gaia](https://github.com/cosmos/gaia/) | I build a gaia image.

## Cluster Description
- This version deploys a single-node cluster with kubeadmin. If needed, it can be modified to a high-availability cluster with k8s source.

|Role	|Quantity	|Description
|:-|:-|:-|
|Deployment Node	|1	|Runs ansible commands, reused as the first master node|
|etcd Nodes	|1	|Note: reused as master nodes|
|Master Nodes	|1	|A cluster with 1 master nodes;4c8g;|
|Node Nodes	|2	|Nodes running application workloads; machine configuration can be upgraded/increased as needed; 8c16g for cosmos|



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

- run ansible-playbook
`sudo ansible-playbook playbooks/setup_kubernetes.yml`



<img width="1237" alt="image" src="https://github.com/user-attachments/assets/cd6a0d1a-bf71-4d6b-9420-b4ebe87a4809">

<img width="1459" alt="image" src="https://github.com/user-attachments/assets/c27aca6a-c17f-4886-b3fb-f54b7244f791">

<img width="1051" alt="image" src="https://github.com/user-attachments/assets/2ebf1a84-4085-494c-bd48-194d13cc6d9a">



Cosmos is read once the ansible playbook done

<img width="1112" alt="image" src="https://github.com/user-attachments/assets/6331e85a-29e0-4bfd-b41b-b3c8f6518d9c">

<img width="507" alt="image" src="https://github.com/user-attachments/assets/10e98ce8-501a-4349-80cc-6a4d9c78dd9a">


Grafana and prometheus

<img width="1171" alt="image" src="https://github.com/user-attachments/assets/438ab34e-b381-4706-8ff6-f0389fb7da52">

<img width="1441" alt="image" src="https://github.com/user-attachments/assets/1f8b47e0-8a38-49d6-9ab8-1a2c7d1fba5d">


For gaia-0 cpu/memory
<img width="1489" alt="image" src="https://github.com/user-attachments/assets/865ab2aa-440c-4390-9e18-d1498e3dbb44">


Grafana dashboard
[http://54.90.137.176:30300/dashboards](http://3.92.245.191:30300/login)
username:admin
password:admin


## Todo list

- Run ansible with runner 
- Timezone Sync (chrony)
- Test cases
- Support HA with master node
- Support HA with etcd
- Support different network: calico, cilium, flannel, kube-ovn, kube-router
- Upgrade/remove support
- Build k8s from source code
- Full env for cosmos peer to peer
- Other requirements(kubernetes-sigs/metrics-server load-balancer docker runtime )
  






  




