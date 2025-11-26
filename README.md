# Lab Project: Cloud-Native App for Best Buy

## Overview
You have been hired as a **Full-Stack Cloud-Native Developer** at Best Buy to build a demo cloud-native application. You will design, develop, and deploy a microservices-based application using the **Algonquin Pet Store (On Steroids)** architecture.

The application should consists of 5 microservices:
*   **Store-Front**: Customer web app.
*   **Store-Admin**: Employee web app.
*   **Order-Service**: Order processing API.
*   **Product-Service**: Product management API.
*   **Makeline-Service**: Background worker for order processing.
*   **Database**: MongoDB (Stateful).

## Requirements

### 1. Microservices Development
*   Fork the [Algonquin Pet Store (On Steroids)](https://github.com/ramymohamed10/algonquin-pet-store-on-steroids) repositories. Use that as a starting point, if you want to.
*   Build and containerize all 5 services.
*   **Commit changes frequently with meaningful messages** to show your progress in all repositories. This will also be used for marking.

### 2. Kubernetes Deployment
*   Deploy all services to a Kubernetes cluster (AKS).
*   Use **ConfigMaps** and **Secrets** for configuration.
*   Use **StatefulSets** for MongoDB.

### 3. CI/CD Pipeline
*   Implement a CI/CD pipeline for **each microservice** to automate building and deployment.
*   **Test the pipeline** for each microservice. GitHub Actions will be used for verification and marking.

## Deliverables

### 1. GitHub Repository
Your repository must contain:
*   **`README.md`**:
    *   Updated Architecture Diagram (Draw.io).
    *   Brief application explanation.
    *   Deployment instructions.
    *   **Links Table**: Repository links and Docker Hub image links for all services.
*   **`Deployment Files/`**: A folder containing all Kubernetes YAML manifests.

### 2. Demo Video
*   Record a **15-minute (max)** video. Treat this as a **pitch to your manager** to sell the application.
*   **Video Content**:
    1.  **Pitch & Architecture**: Start by explaining the architecture and the reasons behind your design choices.
    2.  **App Demo**: Show the application running on the cluster and demonstrate its functionality.
    3.  **CI/CD Demo**: Demonstrate the CI/CD pipeline in action for **at least one service**.
*   Upload to YouTube and add the link to your `README.md`.

## Grading Criteria

| Criteria | Weight |
| :--- | :--- |
| Application Code & Documentation | 25% |
| Kubernetes Deployment | 25% |
| CI/CD Pipeline Implementation | 25% |
| Demo Video | 25% |

### Bonus Marks
Students who do exceptionally well in going above and beyond in this project and deliver an impressive demo can get **up to 5 marks bonus** added to their final grade.

## Submission
*   Submit the repository link via Brightspace.
