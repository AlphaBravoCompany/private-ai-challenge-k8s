# Ollama Kubernetes Deployment

## Overview

This repository hosts the Kubernetes configuration files necessary for deploying the Ollama application within a Kubernetes environment.

## Architecture

The Kubernetes deployment consists of several components outlined in the YAML files within the project. The key components include:

- **WebUI Deployment**: Manages the frontend serving the user interface.
- **Ollama Deployment**: Manages the backend Ollama service.
- **Persistent Volume Claim (PVC)**: Handles data persistence for the application.
- **Service**: Defines the policies to access the WebUI and Ollama services.
- **Ingress**: Manages external access to the services within the cluster.

## Prerequisites

Ensure the following tools and configurations are ready before deployment:

- A Kubernetes cluster
- kubectl configured to interact with your cluster
- Docker installed (for local container image management, if necessary)

## Deployment

To deploy the Ollama application to your Kubernetes cluster, execute the following steps:

1. Clone this repository to your local machine.
2. Apply the configurations to your cluster using kubectl:
   ```bash
   kubectl apply -f ingress.yml
   kubectl apply -f service.yaml
   kubectl apply -f webui-deployment.yml
   kubectl apply -f ollama-deployment.yml
   kubectl apply -f pvc.yml
   ```

- You must set the ENV VAR `HOSTNAME` within the ingress.yml to the hostname of your lab server.

## Accessing the Application

After deployment, the application can be accessed through the configured Ingress endpoint. To view the details and access the services, use the following command:
```bash
kubectl get ingress
```

This will provide the URLs and paths to access the WebUI and other services.