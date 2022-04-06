## What is K3s?

> K3s is a fully compliant Kubernetes distribution with the following enhancements:

1. Packaged as a single binary.
2. Lightweight storage backend based on sqlite3 as the default storage mechanism etcd3, MySQL, Postgres also still available.
3. Wrapped in simple launcher that handles a lot of the complexity of TLS and options.
4. Secure by default with reasonable defaults for lightweight environments.
5. Simple but powerful “batteries-included” features have been added, such as: a local storage provider, a service load balancer, a Helm controller, and the Traefik ingress controller.
6. Operation of all Kubernetes control plane components is encapsulated in a single binary and process. This allows K3s to automate and manage complex cluster operations like distributing certificates.
7. External dependencies have been minimized (just a modern kernel and cgroup mounts needed). K3s packages required dependencies, including:
    * containerd
    * Flannel
    * CoreDNS
    * CNI
    * Host utilities (iptables, socat, etc)
    * Ingress controller (traefik)
    * Embedded service loadbalancer
    * Embedded network policy controller

## What’s with the name?
> rancher wanted an installation of Kubernetes that was half the size in terms of memory footprint. Kubernetes is a 10-letter word stylized as K8s.
> So something half as big as Kubernetes would be a 5-letter word stylized as K3s. 
> There is no long form of K3s and no official pronunciation.