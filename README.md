# Amazon EKS Fargate Deployment with AWS Load Balancer Controller

## Project Overview

This project demonstrates deployment of a containerized application on Amazon EKS using AWS Fargate and AWS Load Balancer Controller.

The application deployed is the Kubernetes 2048 sample application exposed through an internet-facing Application Load Balancer (ALB).

---

## Architecture

User
  |
  v
AWS ALB
  |
Ingress
  |
Service
  |
Deployment
  |
Pods on AWS Fargate

---

## Technologies Used

- AWS EKS
- AWS Fargate
- AWS IAM
- Kubernetes
- kubectl
- eksctl
- AWS Load Balancer Controller
- Helm

---

## Project Steps

### 1. Create EKS Cluster

```bash
eksctl create cluster \
--name demo-cluster1 \
--region us-east-1 \
--fargate
```

### 2. Create Fargate Profile

```bash
eksctl create fargateprofile \
--cluster demo-cluster1 \
--region us-east-1 \
--name alb-sample-app \
--namespace game-2048
```

### 3. Install AWS Load Balancer Controller

Installed using Helm.

### 4. Deploy 2048 Application

```bash
kubectl apply -f manifests/2048_full.yaml
```

### 5. Verify Resources

```bash
kubectl get pods -A
kubectl get ingress -n game-2048
```

---

## Application Access

Application is exposed using AWS ALB.

---

## Screenshots

See screenshots folder.

---

## Repository Structure

```text
.
├── README.md
├── manifests
│   └── 2048_full.yaml
├── docs
│   └── troubleshooting.md
└── screenshots
```

---

## Author

Prameet Kumar

DevOps Learning Project
