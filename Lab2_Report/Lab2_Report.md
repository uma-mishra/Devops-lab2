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
```

## 4.3 Docker Image Build and Container

The Docker image was built successfully using the Dockerfile.

Command used:

```bash
docker build -t sample-flask-app .
```

The image was successfully created as `sample-flask-app:latest`.

The container was started using:

```bash
docker run -d --name sample-flask-container -p 5000:5000 sample-flask-app
```

The application was tested using `curl http://localhost:5000` and returned the expected message.

## 4.4 Docker Image Layers

The `docker history sample-flask-app` command was used to view the image layers. The output showed layers for the base Python image, WORKDIR, COPY, Flask installation, EXPOSE, and CMD instructions.

## 5. Docker Image Management and Docker Compose

The Docker image was tagged as `sample-flask-app:v1` and pushed to Docker Hub as `umamishra0929/sample-flask-app:v1`.

Docker Compose was used to run two containers from the same image. The web container was mapped to port 5001.

The application was tested using `curl http://localhost:5001`.

## 6. Docker Storage

Docker storage was demonstrated using a named volume and a bind mount.

The named volume `my-storage-volume` was used to store data persistently. The data was available again when the volume was mounted in another container.

A bind mount was also tested using the `bind-data` directory. The stored file was successfully read from the container.

## 7. Docker Networking

A custom Docker network named `lab-network` was created. Two containers named `network-client` and `network-server` were connected to the network.

Communication was tested using the container name and the server IP address. Both tests completed successfully with 0% packet loss.

## 8. Kubernetes Deployment

A Kubernetes Deployment and Service were created using `deployment.yaml` and `service.yaml`.

The Deployment was configured with 2 replicas. The application was deployed on Minikube and the pods were verified as Running.

The Service was created using NodePort so that the application could be accessed through Minikube.

## 9. Rolling Update, Scaling and Rollback

A rolling update was performed by changing the image of the Deployment.

The rollout status and rollout history were checked successfully.

The Deployment was then scaled from 2 replicas to 4 replicas. The result showed 4 desired and 4 available replicas.

A rollback was performed using `kubectl rollout undo` and the rollout completed successfully.

## 10. Jenkins Continuous Deployment

Jenkins was used to automate the Kubernetes deployment.

The Jenkins pipeline contains Build, Test, Deploy to Kubernetes, and Verify Deployment stages.

The Lab 2 Jenkins job was `devops-lab2-pipeline`. Build #4 completed successfully and was shown as the last stable and last successful build.

The pipeline applied the Kubernetes Deployment and Service manifests to Minikube and verified deployments, pods, and services.

## 11. Observations

- Docker successfully created and ran the Flask application.
- Docker image layers were visible using `docker history`.
- Docker Compose successfully ran multiple containers.
- Named volumes and bind mounts provided persistent storage.
- Docker containers communicated successfully through the custom network.
- Kubernetes successfully managed application replicas through a Deployment.
- Rolling update, scaling and rollback operations were completed successfully.
- Jenkins successfully automated the Kubernetes deployment process.

## 12. Conclusion

This lab provided practical experience with Docker containerization, Docker Compose, storage, networking, Kubernetes orchestration, Minikube, and Jenkins continuous deployment. The experiments showed how containers can be created, managed, connected, stored, deployed and updated using commonly used DevOps tools.

## 13. Evidence / Screenshots

Screenshots collected during the experiment include:

1. Docker image build and container execution
2. Docker image layers using `docker history`
3. Docker Compose containers
4. Docker named volume and bind mount
5. Docker network communication
6. Kubernetes pods and service
7. Kubernetes rolling update, scaling and rollback
8. Jenkins Lab 2 successful build
