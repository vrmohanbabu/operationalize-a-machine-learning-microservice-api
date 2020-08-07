[![CircleCI](https://circleci.com/gh/vrmohanbabu/operationalize-a-machine-learning-microservice-api.svg?style=svg)](https://circleci.com/gh/vrmohanbabu/operationalize-a-machine-learning-microservice-api)

## Project Overview

In this project, you are given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). In this project the `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

---

## Setup the Environment

* Environment used is Ubuntu16 in cloud9.
* Create a virtualenv and activate it
* Run `make install` to install the necessary dependencies

### Install Minikube through docker

* `curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 \&& chmod +x minikube`
* `sudo mkdir -p /usr/local/bin/`
* `sudo install minikube /usr/local/bin/`
* `minikube start --driver=docker`

### Install hadolint:

`sudo wget -O /bin/hadolint https://github.com/hadolint/hadolint/releases/download/v1.16.3/hadolint-Linux-x86_64 &&\
            sudo chmod +x /bin/hadolint`
            
### Install kubectl:

* `sudo apt-get update && sudo apt-get install -y apt-transport-https gnupg2
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee -a /etc/apt/sources.list.d/kubernetes.list`
* `sudo apt-get update`
* `sudo apt-get install -y kubectl`
* `snap install kubectl --classic`
* `kubectl version --client`

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Upload to Docker Hub: `./upload_docker.sh`
4. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl
