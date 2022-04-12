## Setup k3s single master cluster with script

## Step1: on master node only 
```
sudo curl -sfL https://get.k3s.io | INSTALL_K3S_CHANNEL=latest sh -
```
### [customize installation](https://rancher.com/docs/k3s/latest/en/installation/install-options/#options-for-installation-with-script)



## Step2: on all worker node

#### First run the below command **`k3s on master`** to get the values 
1. sudo hostname -i        -->  copy/note the ipaddr of master node
2. sudo cat /var/lib/rancher/k3s/server/node-token     --> copy / note the token 

#### Execute below on all worker nodes 
```
sudo export K3S_URL=https://master-node-ip:6443
sudo export K3S_TOKEN="node-token copied from master node"

sudo curl -sfL https://get.k3s.io | INSTALL_K3S_CHANNEL=latest sh -
```