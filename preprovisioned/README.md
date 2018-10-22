# All Things Open Provisioned GCP Accounts

## Login to the workshop dev instance

1. Login to the [Google Cloud Console](https://console.cloud.google.com/compute/instances)
   using the provided username and password.
   - If you are already logged in with a different account - login with an incognito window.
1. Select the *All Things Open - K8S WS* project from the drop down
1. Select *continue*
1. Select the *kubebuilder-workshop* instance
1. Select the *SSH* button under *Remote access*

**Note:** Alternatively, login using
 
 1. `gcloud auth login`
 1. `gcloud compute ssh kubebuilder-workshop`

## Configure a local minikube cluster

From the dev instance, use the provided script to setup a local minikube cluster.

```bash
setup-minikube.sh
```

## Setup the go project

From the dev instance, use the provided script to clone the prereqs project.

```bash
setup-project.sh
export GOPATH=$HOME/go
cd go/src/github.com/pwittrock/kubebuilder-workshop-prereqs/
make
```

## Start kubebuilding

Return to the [workshop](https://github.com/pwittrock/kubebuilder-workshop#overview)
