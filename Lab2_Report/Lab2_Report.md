# DEVOPS FOUNDATIONS & CONTINUOUS INTEGRATION
## LAB 2: CONTAINERIZATION & KUBERNETES ORCHESTRATION

**Name:** Uma Mishra  
**Student ID:** 2301730304  
**Lab Code:** ENSP461  
**Program:** B.Tech CSE (AI/ML)  
**Experiment:** Containerization & Kubernetes Orchestration  

---

# 1. Introduction

This laboratory experiment demonstrates containerization and Kubernetes orchestration using Docker, Docker Compose, Minikube, Kubernetes manifests, and Jenkins Continuous Deployment.

The experiment includes Docker image creation, container management, Docker storage, Docker networking, Docker Compose, Kubernetes deployment and services, rolling updates, rollback, replica scaling, and automated Kubernetes deployment through Jenkins.

---

# 2. Tools and Technologies Used

- Docker
- Docker Compose
- Minikube
- Kubernetes
- kubectl through Minikube
- Jenkins
- Git
- GitHub
- Python
- Flask
- Alpine Linux container

---

# 3. System Architecture

The implemented architecture consists of the following components:

1. A sample Flask application was created using Python.
2. A Dockerfile was used to containerize the Flask application.
3. The Docker image was built and executed as a Docker container.
4. The image was tagged and pushed to Docker Hub.
5. Docker Compose was used to run multiple containers.
6. Docker volumes and bind mounts were used for persistent storage.
7. A custom Docker bridge network was created for container-to-container communication.
8. Kubernetes Deployment and Service manifests were created.
9. The application was deployed on a Minikube cluster.
10. Kubernetes rolling update, rollback, and replica scaling were demonstrated.
11. Jenkins was integrated with GitHub to automatically apply Kubernetes manifests.
12. Jenkins successfully verified the Kubernetes deployment.

---

# 4. Docker Containerization

## 4.1 Flask Application

A simple Flask application was created in `app.py`.

The application runs on port 5000 and returns:

`Hello from Docker! Container is running successfully.`

## 4.2 Dockerfile

The application was containerized using the following Dockerfile:

```dockerfile
FROM python:3.12-slim

WORKDIR /app

COPY app.py .

RUN pip install flask

EXPOSE 5000

CMD ["python", "app.py"]
