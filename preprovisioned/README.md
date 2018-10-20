# Instructions for using a provisioned workshop development machine

## Login to the dev machine

1. Login to the [Google Cloud Console](https://console.cloud.google.com/compute/instances)
  using the provided username and password
1. Select the *All Things Open - K8S WS* project from the drop down
1. Select the *kubebuilder-workshop* instance
1. Select the *SSH* button under *Remote access*

## Configure a local minikube cluster

Use the provided script to setup a local minikube cluster.

```bash
setup-minikube.sh
```

## Setup the go project

Use the provided script to clone the prereqs project.

```bash
setup-project.sh
export GOPATH=$HOME/go
cd go/src/github.com/pwittrock/kubebuilder-workshop-prereqs/
make
```

## Start kubebuilding

Return to the [workshop](https://github.com/pwittrock/kubebuilder-workshop#overview)
