# Kubernetes Cluster Monitoring with Prometheus and Grafana

## Introduction
This project sets up monitoring for a Kubernetes cluster using Prometheus and Grafana. Prometheus is used for collecting and querying metrics, while Grafana is used for visualization and monitoring dashboards.

## Prerequisites
Before installing Prometheus and Grafana, ensure you have the following prerequisites installed:
- Docker
- Minikube
- Helm

## Installation
### Docker
Remove any old versions of Docker and then install Docker using the following steps:

Sure, here's a README file for your project:

csharp
Copy code
# Kubernetes Cluster Monitoring with Prometheus and Grafana

## Introduction
This project sets up monitoring for a Kubernetes cluster using Prometheus and Grafana. Prometheus is used for collecting and querying metrics, while Grafana is used for visualization and monitoring dashboards.

## Prerequisites
Before installing Prometheus and Grafana, ensure you have the following prerequisites installed:
- Docker
- Minikube
- Helm

## Installation
### Docker
Remove any old versions of Docker and then install Docker using the following steps:
sudo yum remove docker
docker-client
docker-client-latest
docker-common
docker-latest
docker-latest-logrotate
docker-logrotate
docker-engine
sudo yum install -y yum-utils
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
sudo yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
sudo systemctl start docker


### Minikube
Install and start Minikube using the following steps:
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-latest.x86_64.rpm
sudo rpm -Uvh minikube-latest.x86_64.rpm
minikube start


### Helm
Install Helm using the following steps:
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
chmod 700 get_helm.sh
./get_helm.sh


## Deploying Prometheus and Grafana

### Prometheus
Deploy Prometheus using Helm:
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
helm install prometheus prometheus-community/prometheus
kubectl expose service prometheus-server --type=NodePort --target-port=9090 --name=prometheus-np


### Grafana
Deploy Grafana using Helm:
helm repo add grafana https://grafana.github.io/helm-charts
helm repo update
helm install grafana grafana/grafana
kubectl expose service grafana --type=NodePort --target-port=3000 --name=grafana-np


## Accessing the Services
You can access Prometheus and Grafana using the NodePort IP at ports 9090 and 3000 respectively:
- `minikube ip`:9090 # Prometheus
- `minikube ip`:3000 # Grafana

## Conclusion
Congratulations! You have successfully set up Prometheus and Grafana for monitoring your Kubernetes cluster. With Grafana deployed, you can now configure dashboards to visualize various cluster metrics and gain insights into the health and performance of your Kubernetes environment.

