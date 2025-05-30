# 🚀 Local CI/CD Pipeline: Jenkins + Docker + Kubernetes (Minikube)

## ✅ Objective
To build a fully automated CI/CD pipeline that deploys a Flask web app from GitHub to a local Kubernetes cluster using Jenkins, Docker, and Minikube.

## 🛠️ Tools Used
- Jenkins (CI/CD Automation)
- Docker (Containerization)
- Minikube (Kubernetes cluster)
- GitHub (Source code)
- kubectl (K8s CLI)

## 📁 Project Structure

## 🔁 CI/CD Pipeline Flow
1. Developer pushes code to GitHub
2. Jenkins builds Docker image
3. Jenkins deploys app to Minikube using `kubectl apply`
4. App runs at `http://localhost:30007`

## 🧪 How to Run Locally
```bash
# Start Minikube
minikube start

# Apply Kubernetes manifests
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml

# Access the app
minikube service flaskapp-service

