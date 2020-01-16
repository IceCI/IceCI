# iceci - chill out and integrate

![iceci](img/icecidark.png)


## Run in minikube or local cluster

Create namespace and switch to it

```shell script
kubectl create ns iceci
kubectl config set-context --current --namespace=iceci
```

**IMPORTANT** - in alpha1 namespace is still hardcoded in some places - you have to have **iceci** namespace or it will not work. You have been warned ;)

To deploy the kubernetes operator and its CRD run:

```shell script
kubectl apply -f manifests/crds
kubectl apply -f manifests/operator
```

The UI, database, API and Sync components are deployed independently as the operator can run standalone and users can run pipelines monitor pipelines by `kubectl` tool.

```shell script
kubectl apply -f manifests/app
```

The setup assumes the ingress controller is running on your kubernetes host. It creates ingress rule without *host* routing. You can change it in the *ingress* configuration.
