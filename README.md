# Trend DevOps Project

## Project Overview

This project demonstrates a complete DevOps workflow by deploying the Trend application on AWS using Docker, Jenkins, Kubernetes (EKS), and Terraform.

## Technologies Used

* AWS EC2
* AWS EKS
* Docker
* DockerHub
* Jenkins
* Kubernetes
* GitHub
* Terraform

## Project Architecture

GitHub → Jenkins → Docker Build → DockerHub → Kubernetes Deployment → AWS EKS

## Docker

### Build Image

```bash
docker build -t wahid581doc/trend-app:v1 .
```

### Run Container

```bash
docker run -d -p 3000:80 trend-app
```

## Kubernetes Deployment

### Deployment

```bash
kubectl apply -f deployment.yaml
```

### Service

```bash
kubectl apply -f service.yaml
```

### Verify

```bash
kubectl get pods
kubectl get svc
```

## EKS Cluster

Cluster Name: trend-cluster

### Verify Nodes

```bash
kubectl get nodes
```

## Jenkins CI/CD

Pipeline Stages:

1. Checkout Source Code
2. Build Docker Image
3. Push Docker Image
4. Deploy to Kubernetes

## Application URL

LoadBalancer URL:

http://a4d1016a5363244699fb02d436df24e2-571871970.ap-south-1.elb.amazonaws.com

## Screenshots

* EC2 Instance Running
* Jenkins Dashboard
* Docker Build
* DockerHub Repository
* EKS Cluster
* Kubernetes Pods
* Kubernetes Services
* Jenkins Pipeline Success
* Application Running

## Author

Abdul Wahid
