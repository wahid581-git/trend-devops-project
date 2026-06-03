# Trend Application Deployment using Docker, Jenkins, Terraform and AWS EKS

## Project Overview

This project demonstrates the deployment of a production-ready web application using DevOps tools and AWS cloud services.

The application was containerized using Docker, stored in DockerHub, deployed to Amazon EKS, and automated through a Jenkins CI/CD pipeline integrated with GitHub webhooks.

---

## Architecture

GitHub → Jenkins → Docker Build → DockerHub → Kubernetes Deployment → Amazon EKS → LoadBalancer

---

## Technologies Used

* AWS EC2
* AWS EKS
* Docker
* DockerHub
* Jenkins
* Kubernetes
* Terraform
* Git & GitHub
* Nginx

---

## Repository Information

### Application Repository

GitHub Repository:

https://github.com/wahid581-git/trend-devops-project

### Docker Repository

DockerHub Repository:

https://hub.docker.com/r/wahid581doc/trend-app

Docker Image:

wahid581doc/trend-app:v1

---

## Application Deployment

The application repository was cloned from:

https://github.com/Vennilavanguvi/Trend.git

The repository contained production-ready build files located in the `dist` directory.

The application was deployed using Nginx inside a Docker container.

---

## Docker Configuration

### Build Docker Image

```bash
docker build -t trend-app .
```

### Tag Docker Image

```bash
docker tag trend-app:latest wahid581doc/trend-app:v1
```

### Push Docker Image

```bash
docker push wahid581doc/trend-app:v1
```

---

## Terraform Configuration

Terraform configuration files were created to provision AWS infrastructure.

Files:

* terraform/main.tf
* terraform/variables.tf
* terraform/outputs.tf

### Terraform Commands

```bash
terraform init
terraform validate
```

Terraform validation completed successfully.

---

## Kubernetes Deployment

### Deployment Manifest

deployment.yaml

### Service Manifest

service.yaml

### Deployment Commands

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

### Verify Deployment

```bash
kubectl get pods
kubectl get svc
kubectl get nodes
```

---

## Jenkins CI/CD Pipeline

### Installed Plugins

* Git Plugin
* Docker Plugin
* Pipeline Plugin
* Kubernetes Plugin
* GitHub Integration Plugin

### Pipeline Stages

1. Checkout Source Code
2. Build Docker Image
3. Deploy Application to Kubernetes

### GitHub Webhook

GitHub webhook was configured to automatically trigger Jenkins builds whenever code is pushed to the repository.

---

## EKS Cluster Information

Cluster Name:

trend-cluster

Region:

ap-south-1

### Verify Cluster

```bash
eksctl get cluster
kubectl get nodes
```

---

## Application Access

### EC2 Public URL

http://<EC2-PUBLIC-IP>

### Kubernetes LoadBalancer URL

http://a4d1016a5363244699fb02d436df24e2-571871970.ap-south-1.elb.amazonaws.com

---

## LoadBalancer Information

### LoadBalancer DNS

a4d1016a5363244699fb02d436df24e2-571871970.ap-south-1.elb.amazonaws.com

### LoadBalancer ARN

<PASTE-YOUR-LOADBALANCER-ARN-HERE>

---

## Monitoring

Cluster health was verified using:

```bash
kubectl get pods
kubectl get nodes
kubectl get svc
```

Jenkins pipeline execution was used to monitor deployment status and application health.

## Monitoring Setup

Prometheus monitoring stack was deployed in the EKS cluster using Helm.

Commands Used:

```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update

kubectl create namespace monitoring

helm install monitoring prometheus-community/kube-prometheus-stack \
-n monitoring

---

## Project Outcome

Successfully implemented:

* Docker Containerization
* DockerHub Integration
* Terraform Configuration
* Jenkins CI/CD Pipeline
* GitHub Webhook Integration
* Kubernetes Deployment
* Amazon EKS Cluster
* AWS LoadBalancer Service
* Automated Application Deployment

The application was successfully deployed and made accessible through both the EC2 Public IP and the Kubernetes LoadBalancer endpoint.
