# Frontend and Backend Deployment and Service on Kubernetes

This `README.md` file provides detailed instructions and explanations for deploying frontend and backend applications using Kubernetes. The provided Kubernetes manifests include Deployments and Services for both frontend and backend.

## Table of Contents

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Kubernetes Manifests](#kubernetes-manifests)
   - [Frontend Deployment](#frontend-deployment)
   - [Frontend Service](#frontend-service)
   - [Backend Deployment](#backend-deployment)
   - [Backend Service](#backend-service)
4. [Applying the Manifests](#applying-the-manifests)
5. [Verification](#verification)
6. [Cleanup](#cleanup)

## Introduction

This project sets up frontend and backend applications using Kubernetes. The setup includes:

- Deployments to manage the application's pods.
- Services to expose the applications to external traffic.

The frontend application runs on port 3000 inside the container, and it is exposed on port 80 on the NodePort. The backend application runs on port 3001 inside the container, and it is also exposed on port 80 on the NodePort.

## Prerequisites

Before you begin, ensure you have the following:

- A running Kubernetes cluster.
- `kubectl` command-line tool installed and configured to communicate with your cluster.

## Kubernetes Manifests

### Frontend Deployment

The Frontend Deployment manifest (`frontend-deployment.yaml`) describes how to deploy and manage the frontend application.

### Frontend Service

The Frontend Service manifest (`frontend-service.yaml`) exposes the frontend application to external traffic.

### Backend Deployment

The Backend Deployment manifest (`backend-deployment.yaml`) describes how to deploy and manage the backend application.

### Backend Service

The Backend Service manifest (`backend-service.yaml`) exposes the backend application to external traffic.

## Applying the Manifests

To apply the manifests and deploy the applications, follow these steps:

```sh
# Apply the Frontend Service
kubectl apply -f frontend-service.yaml
```sh
# Apply the Backend Deployment
kubectl apply -f backend-deployment.yaml
```sh
# Apply the Backend Service
kubectl apply -f backend-service.yaml
# Check the frontend deployment
kubectl get deployments
```sh
# Check frontend pods
kubectl get pods
```sh
# Check the frontend service
kubectl get services
```sh
# Check the backend deployment
kubectl get deployments
```sh
# Check backend pods
kubectl get pods
```sh
# Check the backend service
kubectl get services
```sh
# Access the frontend application
kubectl get svc frontend-service
```sh
# Access the backend application
kubectl get svc backend-service
