# Frontend Deployment and Service on Kubernetes

This `README.md` file provides detailed instructions and explanations for deploying a frontend application using Kubernetes. The provided Kubernetes manifests include a Deployment and a Service.

## Table of Contents

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Kubernetes Manifests](#kubernetes-manifests)
   - [Deployment](#deployment)
   - [Service](#service)
4. [Applying the Manifests](#applying-the-manifests)
5. [Verification](#verification)
6. [Cleanup](#cleanup)

## Introduction

This project sets up a frontend application using Kubernetes. The setup includes:

- A Deployment to manage the application's pods.
- A Service to expose the application to external traffic.

The frontend application runs on port 3000 inside the container, and it is exposed on port 80 on the NodePort.

## Prerequisites

Before you begin, ensure you have the following:

- A running Kubernetes cluster.
- `kubectl` command-line tool installed and configured to communicate with your cluster.

## Kubernetes Manifests

### Deployment

The Deployment manifest (`frontend-deployment.yaml`) describes how to deploy and manage the frontend application.

### Service

The Service manifest (`frontend-service.yaml`) exposes the frontend application to external traffic.

## Applying the Manifests

To apply the manifests and deploy the application, follow these steps:

1. **Apply the Deployment:**
   ```sh
   kubectl apply -f frontend-deployment.yml
2. **Apply the Service:**
   ```sh
   kubectl apply -f frontend-service.yml

## Verification
To verify that the application is running correctly:
1. **Check the deployment**
   ```sh kubectl get deployments
2. **Check pods**
   ```sh
    kubectl get pods
3. **Check the Service**
   ```sh
    kubectl get services
4. **Access the application**
    ```sh kubectl get svc frontend-service


