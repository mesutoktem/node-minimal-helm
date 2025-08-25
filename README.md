# 🚀 Quick Start: Node Project via Helm + Kubernetes

This setup runs a **Node.js project from a PersistentVolume**, always using the **latest Git code**.

Workflow:
1. `initContainer` clones or pulls the repo.  
2. Main container runs the app from the volume.  
3. Restart the deployment to pull new commits.

Follow these commands to deploy and manage your app:

---

### 1️⃣ Create a Namespace
```bash
kubectl create namespace test-temp-1
```

### 2️⃣ Install Helm Chart
```bash
helm install minimal-node ./myapp-chart --namespace test-temp-1
```

### 3️⃣ Restart Deployment (Pull Latest Changes)
```bash
kubectl rollout restart deployment minimal-node --namespace test-temp-1
```
