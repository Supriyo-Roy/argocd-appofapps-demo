🚀 Deploying Applications with Argo CD on Minikube: Embracing the "Apps of Apps" Pattern! 🚀

Argo CD Deployment on Minikube
This repository contains the code and configuration for deploying applications using Argo CD on a Minikube cluster, leveraging the "apps of apps" pattern for efficient application management.

Prerequisites
Minikube installed
kubectl installed
Git installed
Setup Instructions
1. Start Minikube
Start your Minikube cluster with the following command:

sh
Copy code
minikube start
2. Install Argo CD
Create the argocd namespace and install Argo CD using the official installation manifest:

sh
Copy code
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
3. Access Argo CD UI
Forward the Argo CD server port to access the UI:

sh
Copy code
kubectl port-forward svc/argocd-server -n argocd 8080:443
Open your browser and navigate to https://localhost:8080.

4. Login to Argo CD
Get the initial password for the admin user:

sh
Copy code
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -
