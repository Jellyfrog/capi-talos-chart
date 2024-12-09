#

##

```shell
kind create cluster
k get nodes

clusterctl init --infrastructure vsphere --bootstrap talos --control-plane talos
```


## preq

optional stuff but good to have for better auto placement of pods and stuff.

```shell
govc tags.category.create -d "Kubernetes region" k8s-region
govc tags.category.create -d "Kubernetes zone" k8s-zone

govc tags.create -d "Kubernetes Region XXX" -c k8s-region k8s-region-se

govc tags.create -d "Kubernetes Zone XXX ZZZ" -c k8s-zone k8s-region-se-zzzz

govc tags.attach -c k8s-region k8s-region-se /DC1
govc tags.attach -c k8s-zone k8s-region-se-zzzz /DC1
```

##

```shell
clusterctl get kubeconfig onprem-poc > /tmp/kubeconfig
KUBECONFIG=/tmp/kubeconfig k get nodes

```
