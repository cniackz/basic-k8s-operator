### Description:

Operator's Basic Structure

### Links:

* https://github.com/cniackz/public/wiki/How-to-Create-the-Skeleton-of-an-Operator

### Diagram:

![image](https://github.com/user-attachments/assets/5c3fea32-6f09-4c61-bd9b-34789793d316)

### Instructions:

1. Create an empty cluster

```shell
createcluster
```

2. Clone the repository

```shell
rm -rf ~/basic-k8s-operator/
cd; git clone git@github.com:cniackz/basic-k8s-operator.git
cd ~/basic-k8s-operator
make docker-build IMG=radical-123
kind load docker-image docker.io/library/radical-123
```
   
3. Deploy the Operator

```shell
kubectl apply -f ~/basic-k8s-operator/config/manager
kubectl apply -k ~/basic-k8s-operator/config/rbac
kubectl apply -k ~/basic-k8s-operator/config/crd
kubectl apply -f ~/basic-k8s-operator/cr.yaml
```
