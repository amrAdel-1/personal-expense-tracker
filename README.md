# 📘 README: Expense Tracker Project

## 📁 Project Structure
```
personal-expense-tracker/
├── expense-tracker-frontend/       # React frontend
│   ├── Dockerfile                  # Builds frontend image
│   └── k8s/                        # K8s manifests (deployment + service + configmap)
├── expense-api/        # Node.js backend (Express + MongoDB)
│   ├── Dockerfile                  # Builds backend image
│   └── k8s/                        # K8s manifests (deployment + service)
├── Jenkinsfile                     # CI/CD pipeline for Jenkins
```

---

## 🧩 Frontend
- **Tech:** React
- **Dockerized:** Yes (uses `node:18-alpine` for build, `nginx:alpine` for serve)
- **Kubernetes:**
  - Deployment with Nginx and configMap for proxy
  - Service (NodePort)
- **Image:** `amradel2002/expense-frontend:latest`

## 🔙 Backend
- **Tech:** Node.js + Express
- **Database:** MongoDB
- **Dockerized:** Yes
- **Kubernetes:**
  - Deployment and Service (NodePort)
- **Image:** `amradel2002/expense-api:latest`

## ⚙️ CI/CD Pipeline (Jenkins)
- **Build frontend & backend Docker images**
- **Run tests for backend**
- **Push to DockerHub**
- **Deploy to Kubernetes cluster**

## 🚀 How to Run
1. Push to GitHub
2. Jenkins detects the change
3. Jenkins pipeline runs:
   - Checkout
   - Build
   - Test
   - Push
   - Deploy

---

## ✅ Notes
- Make sure Jenkins has access to Docker + kubectl
- `dockerhub-credentials` must be configured in Jenkins
- Cluster must be reachable (Minikube or remote)

---

💬 Project by **Amr Adel**
