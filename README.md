## Prerequisites

To get the most out of this Workshop, users should have:

- A basic understanding of [Go Programming Language](https://golang.org/)
- A basic understanding of [Kubernetes APIs](https://kubernetes.io/docs/user-journeys/users/application-developer/foundational/#section-2)

## Setup a Kubernetes API dev environment

### Install dev tools

Install the dev tools that will be used to build and publish the MongoDB API.

- Install Go 1.10+
  - [go](https://golang.org/)

- Install dep
  - [dep](https://github.com/golang/dep)

- Install kubectl
  - [link](https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl)

- Install kustomize
  - [kustomize](https://github.com/kubernetes-sigs/kustomize)

- Install kubebuilder
  - [kubebuilder](https://book.kubebuilder.io/getting_started/installation_and_setup.html)  

### Create a dev cluster (Pick 1)

Setup a dev cluster.

- Google Kubernetes Engine (GKE) - Remote
  - Install [GKE](https://cloud.google.com/kubernetes-engine/)
  - Create the cluster `gcloud container clusters create "test-cluster"`
  - Fetch the credentials for the cluster `gcloud container clusters get-credentials test-cluster`
  - Test the setup `kubectl get nodes`

- Minikube - Local VM
  - Install [minikube](https://github.com/kubernetes/minikube)
  - Start a minikube cluster `minikube start`
  - Test the setup `kubectl get nodes`

### Create a kubebuilder project

Create a new go project

- `mkdir -p $HOME/kubebuilder-workshop/src/github.com/my-org/my-project`
- `export GOPATH=$HOME/kubebuilder-workshop`
- `cd $HOME/kubebuilder-workshop/src/github.com/my-org/my-project`

Initialize the project

- `kubebuilder init --domain k8s.io --license apache2 --owner "My Org"`
  - enter `y` to have it run dep for you
  - wait for `dep` to download the go library dependencies (takes ~3-5 minutes)

## Supplementary Resources

Documentation on kubebuilder available here:

- [http://book.kubebuilder.io](http://book.kubebuilder.io)
