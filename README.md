# 🚀 DevOps GitOps Pipeline

A complete modern DevOps pipeline demonstrating:
- Node.js sample app
- Docker for containerization
- Helm-style Kubernetes YAML for deployment (supports ArgoCD)
- Terraform to provision AWS infrastructure
- Jenkins + GitHub Actions for CI/CD automation
- Monitoring via Prometheus & Grafana

## 📦 Tech Stack
- **Node.js**: Sample application
- **Docker**: Container build
- **Terraform**: Provisioning AWS (EKS, EC2)
- **Helm-style YAML**: Kubernetes deployment
- **Jenkins**: CI/CD pipeline
- **GitHub Actions**: Additional automation
- **ArgoCD**: GitOps continuous delivery
- **Prometheus & Grafana**: Monitoring stack

## 🚀 Features
- Automated code pull, dependency checks, build & push Docker image
- Vulnerability scans (Trivy)
- CI on Jenkins with stage separation
- GitOps CD via ArgoCD, automatically syncing manifests to Kubernetes
- Terraform for infra as code
- Helm-style manifests ready for `helm install` or ArgoCD sync
- Optional .tgz chart packaging
- Notification & observability with Prometheus + Grafana dashboards

## 🔥 Getting Started
1. Clone this repo
2. Adjust `values.yaml` (or raw YAML) for your K8s cluster config
3. `terraform init && terraform apply` to provision infra
4. Build & push Docker image (`docker build -t yourrepo/app .`)
5. Configure Jenkins pipeline (or GitHub Actions) with your repo secrets:
   - `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`
   - `GITHUB_TOKEN`, etc.
6. Access ArgoCD and sync the app to deploy
7. Monitor via Prometheus & Grafana

## 📂 Directory Structure

devops-gitops-pipeline/

├── .github/

│   └── workflows/

│       └── ci.yml              # Opsional jika mau pakai GitHub Actions juga

├── jenkins/

│   ├── Jenkinsfile             # Jenkins CI/CD pipeline script

├── terraform/

│   ├── main.tf                 # EC2 / networking

│   └── outputs.tf

├── cloudformation/

│   └── eks-nodegroup.yaml      # Node group CFN template

├── k8s/

│   ├── deployment.yaml         # App Deployment

│   ├── service.yaml            # Service

├── docker/

│   └── Dockerfile              # App Dockerfile

├── app/

│   └── index.js                # Source code sample

│   └── package.json            # Source code sample

├── argocd/

│   └── app.yaml                # ArgoCD Application manifest

└── README.md

## ⚡ Quick Start with Helm
```bash
helm install myapp ./k8s
```
Or if packaged:
```bash
helm install myapp ./myapp-0.1.0.tgz
```

## 📊 Monitoring
- Prometheus scrapes app metrics
- Grafana dashboards auto-imported from config

---

🎉 Enjoy building secure, automated, production-ready CI/CD + GitOps pipelines!
