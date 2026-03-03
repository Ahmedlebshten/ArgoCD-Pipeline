# URL Shortener Webservice – CI/CD on EKS using Jenkins & ArgoCD 

## 📌 Overview
- A simple CI/CD pipeline that builds a Docker image using Jenkins and deploys it automatically to an Amazon EKS cluster using ArgoCD (GitOps).

____

## 🏗 Architecture Flow
Jenkins (CI)
- Builds Docker image from Dockerfile
- Pushes image to Docker Hub
ArgoCD (CD)
- Watches a GitHub repo containing Helm chart
- Syncs changes automatically to EKS
- Deploys the updated app
- EKS (Kubernetes)
- Runs the application
- Exposes it using a LoadBalancer Service

## 🏗️ Repo Structure
```
project-root/
│
├── ArgoCD-Application/
│   ├── Jenkinsfile
│   ├── deployment.yaml
│   └── service.yaml
│
├── monitoring/
│   ├── Jenkinsfile
│   ├── grafana.yaml
│   ├── loki.yaml
│   ├── prometheus.yaml
│   └── promtail.yaml
│
└── README.md
```
____

## How Deployment Works
- Update code → Jenkins builds & pushes image
- Update Helm chart repo → ArgoCD auto-syncs
- EKS rolls out the new version automatically

____

## Access App:
```
kubectl get svc
```
Copy the DNS of LB and open it in browser.

____

## Tech Stack:
- Jenkins
- Docker
- Git & GitHub
- ArgoCD
- Amazon EKS


    
