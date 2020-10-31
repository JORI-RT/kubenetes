```sh
# minikube start
minikube start --vm-driver virtualbox --cpus=4 --memory=8000
kubectl create ns logging-operator
kubectl apply -k ./operator/logging-operator/config/crd/
kubectl apply -k ./operator/logging-operator/config/rbac/
kubectl apply -f ./operator/logging-operator/config/manager/manager.yaml
kubectl apply -f ./operator/logging-operator/config/samples/



```