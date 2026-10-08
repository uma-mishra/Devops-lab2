# DevOps Lab 2 - Containerization and Kubernetes

## Introduction

This repository contains the work completed for DevOps Lab 2. The lab covers Docker, Docker Compose, Docker storage, Docker networking, Kubernetes using Minikube, and Jenkins continuous deployment.

## Tools Used

- Docker
- Docker Compose
- Kubernetes
- Kubernetes
- Minikube
- Jenkins
- Git and GitHub
- Python
- Flask

## Lab Work

### Docker
A simple Flask application was containerized using a Dockerfile. The image was built, a container was run, and the application was tested through localhost.

### Docker Compose
Docker Compose was used to run multiple containers using the same application image.

### Docker Storage
A Docker named volume and a bind mount were used to demonstrate persistent data storage.

### Docker Network
Two Docker containers were connected using a custom network. Communication was tested using both container name and IP address.

### Kubernetes
A Kubernetes Deployment and Service were created and deployed using Minikube. Rolling update, rollback, and replica scaling were also performed.

### Jenkins
Jenkins was used to automate the Kubernetes deployment by applying the Kubernetes manifest files and checking the deployment status.

## Files

- `app.py` - Flask application
- `Dockerfile` - Docker image configuration
- `docker-compose.yml` - Docker Compose configuration
- `deployment.yaml` - Kubernetes Deployment
- `service.yaml` - Kubernetes Service
- `Jenkinsfile` - Jenkins pipeline
- `bind-data/` - Bind mount data
- `Lab2_Report/` - Lab report

## Author

Uma Mishra  
B.Tech CSE (AI/ML)
