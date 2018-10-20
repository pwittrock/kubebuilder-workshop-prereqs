# Instructions for getting a Development machine

## Create up a Development machine using DM

Do this if you have a GCP project, but it hasn't been setup for you.

- Install [gcloud](https://cloud.google.com/sdk/install)

```bash
gcloud auth login # login through a browser
gcloud config set project PROJECT
```

```bash
gcloud deployment-manager deployments create kubebuilder-workshop --config workshop.yaml
```

```bash
gcloud compute ssh kubebuilder-workshop

# It may take several minutes for the startup script to complete...
which setup-project.sh || echo "startup script still running, please wait a minute..."
```

Output from the startup script can be viewed here if needed:

```bash
sudo tail -f /var/log/syslog
```

Look for `kubebuilder-workshop startup-script: INFO Finished running startup scripts.`

# Instructions for setting up the workshop Project

## Setup a local minikube cluster

```bash
setup-minikube.sh
```

## Setup the go project

```bash
setup-project.sh
export GOPATH=$HOME/go
cd go/src/github.com/pwittrock/kubebuilder-workshop-prereqs/
make
```

## Start kubebuilding

```bash
kubebuilder create api ...
```