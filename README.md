This is not an officially supported Google product

## Prerequisites

To get the most out of this Workshop, users should have:

- A basic understanding of [Go Programming Language](https://golang.org/)
- A basic understanding of [Kubernetes APIs](https://kubernetes.io/docs/user-journeys/users/application-developer/foundational/#section-2)

## Setup a local Kubernetes API dev environment

The workshop is focused on building a Kubernetes API / Operator from scratch.  Do the following to setup your
development environment.

**Note**: If you have been provided a pre-provisioned GCP project development account see the
[pre-provision instructions](https://github.com/pwittrock/kubebuilder-workshop-prereqs/blob/master/preprovisioned/README.md)
instead.

### Install dev tools

Make sure the following are installed.

- Install Go 1.10+
  - [go](https://golang.org/)

- Install kubebuilder
  - [kubebuilder](https://book.kubebuilder.io/getting_started/installation_and_setup.html)  

- Install kubectl
  - [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl)
  
- (Optional) Install Make
  - [Make](https://www.gnu.org/software/make/)

### Create a dev cluster (Pick 1)

Either:

- Google Kubernetes Engine [GKE](https://cloud.google.com/kubernetes-engine/) - Remote
  - Requires [gcloud](https://cloud.google.com/sdk/gcloud/)
  - Create the cluster `gcloud container clusters create "test-cluster"`
  - Fetch the credentials for the cluster `gcloud container clusters get-credentials test-cluster`
  - Test the setup `kubectl get nodes`

Or:

- Minikube - Local VM
  - Install [minikube](https://github.com/kubernetes/minikube)
  - Start a minikube cluster `minikube start`
  - Test the setup `kubectl get nodes`

### Create a new kubebuilder project (Pick 1)

Either:

- Clone this project (which has already been setup for you)
  - requires [git](https://git-scm.com/downloads)
  - make sure your `GOPATH` is configured to something (e.g. `$HOME/go`)
  - `mkdir -p $GOPATH/src/github.com/pwittrock/`
  - `cd $GOPATH/src/github.com/pwittrock/`
  - `git clone https://github.com/pwittrock/kubebuilder-workshop-prereqs`

Or:

- Create a new project from scratch
    - requires [dep](https://github.com/golang/dep)
    - create the project directory
        - `mkdir -p $HOME/kubebuilder-workshop/src/github.com/my-org/my-project`
        - `export GOPATH=$HOME/kubebuilder-workshop`
        - `cd $HOME/kubebuilder-workshop/src/github.com/my-org/my-project`
    - initialize the project structure
        - `kubebuilder init --domain k8s.io --license apache2 --owner "My Org"`
          - enter `y` to have it run dep for you
          - wait for `dep` to download the go library dependencies (takes ~3-5 minutes)
    - **for workshop only:** copy the [helper functions](https://github.com/pwittrock/kubebuilder-workshop-prereqs/blob/master/pkg/util/util.go)

## Verify your project is setup

- Run `make` from the project

**Note:** If you don't have `make` installed, you can look at the `Makefile` and run go commands manually.

## Supplementary Resources

For those who are interested, there is documentation on kubebuilder available here:

- [http://book.kubebuilder.io](http://book.kubebuilder.io)
