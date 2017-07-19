# vagrant-kubernetes-lab
This project is to provide a simple local Kubernetes cluster with a master and a worker node for testing purpose.

Vagrant was chosen for being able to create the cluster either on linux, windows and mac hosts.

## Prequirements
- Vagrant : https://www.vagrantup.com/downloads.html
- VirtualBox : https://www.virtualbox.org/wiki/Downloads

## Default provisioning
Vagrant up will provide 2 Ubuntu Xenial VMs for a kubernetes cluster with these features by default :
- Kubernetes control plane v1.7.1
- Weave network cni v2.0.0 
- Kubernetes Dashboard v1.6.1
- Heapster v1.3.0 
- Helm v2.5.0

## Kubeconfig
After installation, a copy of the admin.conf generated by kubeadm is available on the host in the vagrant/kubeconfig directory.

Even if kubectl can be used within the guests, it is suggered that you copy the admin.conf as config in your .kube/ directory on the host to able to do kubectl proxy and kubectl port-forward per example.

## Extra features 
Multiple optionnal extra softwares has been tested with this cluster and are available if needed.
Here is the current list by category :
### Ingress
- Nginx ingress controller v0.9.0-beta.8 + Default backend v1.3
### Monitoring
- InfluxDB v1.1.1 + Grafana v4.0.2
- Weavescope v1.5.0
### Networking
- Weave net v2.0.0
- Flannel v0.7.1
### Storage
- Nfs-provisioner v1.0.8
### Helm
- Helm v2.5.0 (tilller)
Installed by default, only helm client is required to fit your host OS : https://github.com/kubernetes/helm/releases
##### Have a look at the README.md in related subdirectories for specific instructions.
