# SQL Server Deployment on Kubernetes

This repository contains YAML files to deploy SQL Server on a Kubernetes cluster with a Deployment, Secrets, and Service.

## Features

- **Deployment:** Single SQL Server pod exposing port `3306` with credentials from a Secret.
- **Headless Service:** Enables pod-to-pod communication using `clusterIP: None`.
- **Secrets:** Stores base64-encoded SQL Server credentials securely.

## Files

- `sqlserver-deployment.yaml`: Defines the Deployment and Service.
- `sqlserver-secret.yaml`: Contains Secrets with credentials.
- `sqlserver-service.yaml`: Defines the Service for SQL Server.

## Prerequisites

- Kubernetes cluster (e.g., Minikube, GKE, EKS).
- `kubectl` CLI configured.

## Usage

1. Apply Secrets:
    ```bash
    kubectl apply -f SQL-Secret-Manifest.yml
    ```
2. Deploy SQL Server:
    ```bash
    kubectl apply -f SQL-Deployment-Manifest.yml
    ```
3. Apply Service:
    ```bash
    kubectl apply -f SQL-Service-Manifest.yml
    ```
4. Verify:
    ```bash
    kubectl get pods
    ```

## Cleanup

Delete resources:
```bash
kubectl delete -f SQL-Deployment-Manifest.yml
kubectl delete -f SQL-Secret-Manifest.yml
kubectl delete -f SQL-Service-Manifest.yml
```