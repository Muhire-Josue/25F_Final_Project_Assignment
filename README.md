# Lab 10 – CI/CD Deployment to AKS (Algonquin Pet Store)

This lab implements a full CI/CD pipeline using **GitHub Actions**, **Docker Hub**, and **Azure Kubernetes Service (AKS)**. Each microservice automatically builds, pushes, and deploys updated container images whenever changes are merged into the `main` branch.

---

## 📌 Updated Architecture Diagram

<img width="1715" height="809" alt="Screenshot 2025-12-08 at 12 53 24" src="https://github.com/user-attachments/assets/abe2aa1d-e59d-4fb1-8d4e-594cf1e81de3" />

---

## 📌 Application Overview

The Algonquin Pet Store is a microservices-based application consisting of:

- **Order Service** – Receives and processes customer orders using RabbitMQ.  
- **Makeline Service** – Handles order workflow and persists data to MongoDB.  
- **Product Service** – Provides product information and integrates with the AI service.  
- **Store Front** – Public-facing UI communicating with Order + Product services.  
- **Store Admin** – Internal UI for staff interacting with Product + Makeline services.  
- **AI Service** – Optional integration for text/image generation.  
- **MongoDB + RabbitMQ** – Backing services deployed inside the AKS cluster.

The CI/CD workflow automates Docker image builds, testing, publishing to Docker Hub, and deployment to AKS.

---

## 📌 Deployment Instructions

### 1. Update the Docker Image
Each service repository uses a GitHub Actions workflow (`ci_cd.yaml`) that:

1. Builds the new Docker image  
2. Pushes it to Docker Hub  
3. Updates the AKS deployment automatically using:  
   ```bash
   kubectl set image deployment/$DEPLOYMENT_NAME \
     $CONTAINER_NAME=$DOCKER_USERNAME/$DOCKER_IMAGE_NAME:latest

To verify deployments:

`
kubectl get pods -o wide
`
`
kubectl get services
`
`
kubectl get pods -o wide
`
`
kubectl get services
`

The workflow automatically updates the image using:

```
kubectl set image deployment/$DEPLOYMENT_NAME $CONTAINER_NAME=$DOCKER_USERNAME/$DOCKER_IMAGE_NAME:latest
kubectl rollout restart deployment/$DEPLOYMENT_NAME

```

### Repository & Docker Hub Links

| Service   |      GitHub Repository      |  Docker Hub Image |
|----------|:-------------:|------:|
| Store Front | https://github.com/Muhire-Josue/store-front-L8 | https://hub.docker.com/r/josue009/store-front-l8/tags |
| Store Admin | https://github.com/Muhire-Josue/store-admin-L8 | https://hub.docker.com/repository/docker/josue009/store-admin-l8/general |
| Order Service | https://github.com/Muhire-Josue/order-service-L8 | https://hub.docker.com/repository/docker/josue009/order-service-l8/general |
| Product Service | https://github.com/Muhire-Josue/product-service-L8 | https://hub.docker.com/repository/docker/josue009/product-service-l8/general |
| Makeline Service | https://github.com/Muhire-Josue/makeline-service-L8 |https://hub.docker.com/repository/docker/josue009/makeline-service-l8/general|
| virtual customer | https://github.com/Muhire-Josue/virtual-customer-L8 | https://hub.docker.com/repository/docker/josue009/virtual-customer-l8/general |
| virtual worker | https://github.com/Muhire-Josue/virtual-worker-L8 | https://hub.docker.com/repository/docker/josue009/virtual-worker-l8/general |


### Demo Video

Youtube
