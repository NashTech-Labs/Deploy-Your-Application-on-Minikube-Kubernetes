# Deploy Your Application on Minikube - Kubernetes 

## Overview

This template helps you deploy your application on Minikube using Kubernetes resources such as Deployments and Services. By following this guide, you will be able to quickly set up and run your application in a local Kubernetes environment.

## Prerequisites

Before you begin, ensure you have the following installed:

- Minikube: A local Kubernetes cluster to test and develop your applications.
- kubectl: Kubernetes CLI to interact with your Minikube cluster.
- Docker (Optional, but recommended if you want to build images locally).

Ensure your Minikube cluster is running:

      minikube start
    
## Steps Guide

1. Clone this repository to your local machine.

       git clone <repo_url>
       cd <repo_directory>

2. Update the Deployment File

    In the deploy.yaml file, you need to modify the following placeholders to fit your application:

   - name: Replace my-app with your application's name.
   - image: Replace image-name:tag with your Docker image name and tag.
   - replicas: Set the desired number of replicas for your application.

3. Update the Service File

   In the service.yaml file, you need to modify the following:

   -  name: Replace my-app-service with the name of your service.
   -  port: The port your application will listen on.

4. Apply the configuration
     
   Once you have updated the files with your application's details, you can apply them to your Minikube cluster:
      
          kubectl apply -f deploy.yaml
          kubectl apply -f service.yaml

   You can verify that your deployment is successful by checking the pods:
    
          kubectl get pods

5. Access Your Application

   To access the application locally, use the following command to get the URL:
    
          minikube service app-name-service --url

   This will give you the URL where your application is exposed.
