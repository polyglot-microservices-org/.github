# 🚀 Polyglot Microservices Organization

> **Cloud-native microservices ecosystem with modern DevOps practices and polyglot programming**

## 🌟 Overview

Production-ready microservices architecture built with multiple programming languages, containerized with Docker, orchestrated with Kubernetes, and deployed using GitOps principles.

### 🎯 What This Platform Does

- **📝 Notes Management** - Create, read, update, and delete personal notes
- **✅ Todo Management** - Task management with completion tracking
- **👥 Contact Management** - Personal contact directory with CRUD operations
- **🧠 AI Cheatsheet Generator** - Generate comprehensive cheatsheets using AWS Bedrock
- **📊 Real-time Monitoring** - System metrics and application performance monitoring

## 🏗️ Architecture

| Service | Language | Port | Database | Purpose |
|---------|----------|------|----------|---------|
| **Frontend** | HTML/CSS/JS + Nginx | 30080 | - | Web UI with reverse proxy |
| **User Service** | Go | 5000 | MongoDB | Contact management API |
| **Todo Service** | Python Flask | 5001 | MongoDB | Task management API |
| **Notes Service** | Python Flask | 5002 | MongoDB | Notes management API |
| **AI Cheatsheet** | Python Flask | 5005 | AWS Bedrock | AI content generation |

### Technology Stack
- **Languages**: Go, Python Flask, JavaScript
- **Database**: MongoDB with StatefulSets
- **AI**: AWS Bedrock (Claude 3 Sonnet)
- **Frontend**: Nginx reverse proxy
- **Infrastructure**: Kubernetes, Docker, Terraform
- **CI/CD**: GitHub Actions with self-hosted runners
- **Monitoring**: Prometheus (30090), Grafana (30300)

## 🚀 CI/CD Pipeline

**CI**: GitHub-hosted runners → Docker builds with Git SHA → Push to registry → Update K8s manifests

**CD**: Self-hosted EC2 runners → Zero-downtime rolling updates → Health checks → Auto rollback

## 🐳 Docker

**Multi-stage builds**: Separate build and runtime stages for minimal image sizes

**Security**: Non-root users, minimal base images (Alpine/Python slim)

**Health checks**: Built-in container health monitoring

**Layer optimization**: Efficient caching and minimal layers

**Best practices**: .dockerignore, specific tags, vulnerability scanning

## ☸️ Kubernetes

**Deployments**: Rolling updates, replica management, pod templates

**StatefulSets**: MongoDB persistence with ordered deployment

**Services**: ClusterIP (internal), NodePort (external access)

**PV/PVC**: Persistent volumes for database storage

**ConfigMaps**: Environment configuration and Nginx config

**Secrets**: AWS credentials and sensitive data

**HPA**: Horizontal Pod Autoscaler for CPU/memory-based scaling

**Network Policies**: Default deny ingress, selective allow rules

**Probes**: Liveness, readiness, and startup health checks

**Resource Limits**: CPU and memory requests/limits for all pods

## 🏗️ Infrastructure

**One-Click Deployment**: EC2 → Kubernetes (kubeadm + Weave CNI) → GitHub Runner → App Deployment

**State Management**: S3 backend + DynamoDB locking

## 🔒 Security & Monitoring

**Security**: Network policies, Kubernetes secrets, non-root containers, resource limits

**Monitoring**: Prometheus + Grafana + Node Exporter

## 🚀 Quick Start Guide

### Prerequisites
Set up the following GitHub Secrets in your organization:

```bash
# Docker Hub Credentials
DOCKER_USERNAME=your_dockerhub_username
DOCKER_PASSWORD=your_dockerhub_password

# AWS Credentials
AWS_ACCESS_KEY_ID=your_aws_access_key
AWS_SECRET_ACCESS_KEY=your_aws_secret_key
AWS_REGION=us-east-1

# GitHub Token (with repo and admin:org permissions)
GH_PAT=your_github_personal_access_token
```

### 🎯 One-Click Deployment

1. **Fork all repositories** to your GitHub organization
2. **Navigate to infra-terraform repository**
3. **Run the GitHub Action workflow**:
   ```bash
   Actions → Deploy Infrastructure → Run workflow
   ```

### 🕐 Deployment Timeline
**Total Time**: ~8-12 minutes (Infrastructure + Kubernetes + Applications)

### 🌐 Access Points

| Service | URL | 
|---------|----- |
| **Application** | `http://<node-ip>:30080` |
| **Prometheus** | `http://<node-ip>:30090` |
| **Grafana** | `http://<node-ip>:30300` |

## 🏆 What's Implemented

**Kubernetes**: Deployments, StatefulSets, Services (ClusterIP/NodePort), PV/PVC, ConfigMaps, HPA, Network Policies

**Containers**: Multi-stage builds, health checks, resource limits, non-root users

**DevOps**: Git SHA tagging, rolling updates, Prometheus/Grafana monitoring
## 🏷️ Tags
`microservices` `kubernetes` `docker` `golang` `python` `flask` `mongodb` `aws-bedrock` `terraform` `prometheus` `grafana` `cicd` `github-actions` `devops` `cloud-native` `polyglot` `gitops`

---

**🌟 Star this organization if you find it helpful!**

*Built with ❤️ for the developer community to showcase modern microservices architecture and DevOps practices.*