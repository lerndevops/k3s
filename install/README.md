## Setup k3s single master cluster with script

## Step1: on master node only 
```
curl -sfL https://get.k3s.io | INSTALL_K3S_CHANNEL=latest sh -
```
#### more options: 
1. INSTALL_K3S_CHANNEL=  latest/stable/testing 
2. INSTALL_K3S_VERSION=  Version of K3s to download from Github. Will attempt to download from the stable channel if not specified.
3. INSTALL_K3S_BIN_DIR=  Directory to install K3s binary, links, and uninstall script to, or use /usr/local/bin as the default.

#### [more info on options](https://rancher.com/docs/k3s/latest/en/installation/install-options/#options-for-installation-with-script)


## Step2: on all worker node

> First run the below command **`k3s on master`** to get the values 
1. hostname -i  -- copy the ipaddr of master node
2. cat /var/lib/rancher/k3s/server/node-token

> Execute below on all worker nodes 
```
export K3S_URL=https://master-node-ip:6443
export K3S_TOKEN="node-token copied from master node"

curl -sfL https://get.k3s.io | INSTALL_K3S_CHANNEL=latest sh -
```