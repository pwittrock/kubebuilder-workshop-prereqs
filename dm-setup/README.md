# Instructions for getting a Development machine

## Option 1: login to an existing machine

Do this if you have the username / password for an existing GCP project that has been setup with a Development
instance for you.

- Login to the GCE Console [https://console.cloud.google.com/compute/instances](https://console.cloud.google.com/compute/instances)
- Select the *kubebuilder-workshop* Instance
- Select *SSH*
  - Select *Open in browser window*

## Option 2: create up a Development machine using DM

Do this if you have a GCP project, but it hasn't been setup for you.

- Install [gcloud](https://cloud.google.com/sdk/install)

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
cd $GOPATH/go/src/github.com/pwittrock/kubebuilder-workshop-prereqs/
make
```

## Start kubebuilding

```bash
kubebuilder create api ...
```