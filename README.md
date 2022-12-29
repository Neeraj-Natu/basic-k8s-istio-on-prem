# basic-k8s-istio-on-prem
This repo has manifests to setup k8s and Istio on-prem with NodePort Istio-ingressgateway
(Steps define setting up for windows or mac-os).

### Pre-Requisites

* [Kind](https://kind.sigs.k8s.io/)
* [Docker Desktop CE](https://www.docker.com/products/docker-desktop/) 
* [Kubectl](https://kubernetes.io/docs/tasks/tools/)
* [Istioctl](https://istio.io/latest/docs/setup/install/istioctl/)




### Setting up the clusters :

```
kind create cluster --name=istio-test --config=kind/kind-config.yaml
```

### Setting up istio :

```
istioctl install -f istio/istio-profile.yaml
```

### Deploying echoserver, gateway and virtualservice

```
k apply -f application/manifest.yaml

k apply -f application/gateway.yaml
```
