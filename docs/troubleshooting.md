# Troubleshooting Guide

## Issue 1: AWS CLI Credential Error

### Error

Partial credentials found for profile default

### Resolution

Configured AWS credentials using:

aws configure

---

## Issue 2: CloudFormation Stack Already Exists

### Error

AlreadyExistsException

### Resolution

Verified existing EKS cluster and reused the cluster.

---

## Issue 3: AWS Load Balancer Controller Not Running

### Error

ServiceAccount aws-load-balancer-controller not found

### Resolution

Created IAM Service Account using eksctl.

---

## Issue 4: CoreDNS Pods Pending

### Error

InsufficientNumberOfReplicas

### Resolution

Patched CoreDNS deployment for Fargate scheduling.

---

## Issue 5: Ingress Address Not Generated

### Error

Webhook endpoint unavailable

### Resolution

Verified CoreDNS and AWS Load Balancer Controller configuration.
