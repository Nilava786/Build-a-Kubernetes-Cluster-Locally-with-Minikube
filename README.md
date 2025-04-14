# Build-a-Kubernetes-Cluster-Locally-with-Minikube
Day-5 Task Of Elevate Labs Internship

# 🚀 Build a Kubernetes Cluster Locally with Minikube (Day-5 Task)

## 📌 Objective
Deploy and manage a sample Nginx app on a local Kubernetes cluster using Minikube.

---

## 🛠 Tools & Technologies
- Minikube
- kubectl
- Docker
- VirtualBox
- Ubuntu (WSL2)
- VS Code
- Git & GitHub

---


---

## ⚙️ Prerequisites

Ensure the following tools are installed **inside your WSL2 Ubuntu**:

```bash
sudo apt update
sudo apt install -y curl wget apt-transport-https
sudo apt install -y docker.io
sudo usermod -aG docker $USER
newgrp docker

# Install kubectl
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x kubectl
sudo mv kubectl /usr/local/bin/

# Install Minikube
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube

# Install VirtualBox (on Windows, outside WSL2)


🚀 Commands Used

✅ 1. Start Minikube with VirtualBox driver

minikube start --driver=virtualbox

✅ 2. Check cluster status

kubectl cluster-info
kubectl get nodes

✅ 3. Create Nginx deployment

kubectl apply -f deployment.yaml
kubectl get pods

✅ 4. Expose the deployment via NodePort

kubectl apply -f service.yaml
kubectl get svc

✅ 5. Access the app

minikube service nginx-service --url

✅ 6. Scale deployment to 4 pods

kubectl scale deployment nginx-deployment --replicas=4
kubectl get pods

✅ 7. Inspect logs and pod details

kubectl describe pod <pod-name>
kubectl logs <pod-name>

All screenshots showing each step are located inside the screenshots day-5/ folder