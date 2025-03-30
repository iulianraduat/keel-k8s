# keel-k8s

Keel as k8s deployment

## Install

In the folder were you have all .yaml files run the following command:

```
kubectl apply -k .
```

If it does not work for minikube then try:

```
minikube kubectl apply -k .
```

If it does not work for microk8s then try:

```
microk8s kubectl apply -k .
```

You should see in the `default` namespace defined for kubernetes all the new objects.
The corresponding service is called `keel`.

If you want to use it in a different namespace then just add "-n &lt;namespace&gt;" as argument to kubectl call.

You need to use a proxy in front of it (like nginx) to redirect to the exposed port on k8s node.
To find the mapped ports for port 9300 just check the "Internal Endpoints" of the service "keel"
or run `kubectl get svc` from the shell of the server running the cluster.

## Authentication

You must customize the authentication values in `keel-env-configmap.yaml`.

## Accessign the keel UI

The ui is at `/dashboard`.
