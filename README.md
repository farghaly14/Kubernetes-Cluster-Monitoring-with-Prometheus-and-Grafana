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
'sudo yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine
'
