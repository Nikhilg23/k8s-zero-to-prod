# 🚀 Kubernetes Blue-Green Deployment (Nginx)

This project demonstrates a **Blue-Green Deployment strategy** using Kubernetes and Nginx.

It shows how to run two versions of an application (Blue & Green) simultaneously and route traffic between them using a Kubernetes Service.

---

## 📌 Project Objective

- Deploy two versions of an app (Blue & Green)
- Serve custom HTML pages using ConfigMaps
- Expose application using NodePort
- Demonstrate Kubernetes load balancing
- Understand labels and selectors

---

## 🏗 Architecture

User (Browser)
        ↓
NodeIP:NodePort
        ↓
Kubernetes Service
        ↓
Blue Pod   |   Green Pod

- Both deployments run at the same time
- Service routes traffic using labels
- Refreshing the browser switches between versions

---

## 📂 Project Structure

```
.
├── blue-deployment.yaml
├── green-deployment.yaml
├── service.yaml
└── README.md
```

---

## 🔵 Blue Deployment

- Nginx container
- Custom blue HTML page
- Mounted using ConfigMap
- Label: `version: blue`

---

## 🟢 Green Deployment

- Nginx container
- Custom green HTML page
- Mounted using ConfigMap
- Label: `version: green`

---

## 🌐 Service Configuration

Service Type: **NodePort**

Default NodePort Range:
```
30000 – 32767
```

Example access:
```
http://<NodeIP>:30007
```

If using Minikube:
```
minikube service color-service
```

---

## 🚀 Deployment Steps

### 1️⃣ Apply all configurations

```bash
kubectl apply -f .
```

### 2️⃣ Verify pods

```bash
kubectl get pods
```

### 3️⃣ Check service

```bash
kubectl get svc
```

### 4️⃣ Access application

Open in browser:

```
http://<NodeIP>:<NodePort>
```

Refresh the page to see traffic switching between Blue and Green.

---

## 🔄 How Traffic Switching Works

The Service uses this selector:

```yaml
selector:
  app: color-app
```

Both deployments share the same `app` label, so Kubernetes load balances traffic between them.

---

## 🧠 Key Concepts Learned

- Kubernetes Deployments
- Labels & Selectors
- ConfigMaps
- NodePort Service
- Blue-Green Deployment Strategy
- Basic Load Balancing

---

## 🎯 Future Improvements

- Use ClusterIP + Ingress
- Implement Istio traffic shifting
- Add Horizontal Pod Autoscaler (HPA)
- Deploy to AWS / Azure with LoadBalancer
- Integrate CI/CD pipeline

---

## 🛠 Tech Stack

- Kubernetes
- Docker
- Nginx
- YAML

---

## Additional Cmmd troubleshoot :-
```
kubectl get svc color-service -o yaml
kubectl get pod --show-labels
kubectl get endpoints color-service   
```
## 👨‍💻 Author

**Nikhil (Niks)**  
DevOps Engineer | Learning Kubernetes & Cloud
