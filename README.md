# 🚀 EC2 Monitoring with Prometheus & Grafana (Terraform + Docker Compose)

This project provisions an **AWS EC2 instance** using **Terraform** and deploys a monitoring stack (**Prometheus, Grafana, Node Exporter**) on it using **Docker Compose**.  
The goal is to monitor the EC2 instance itself in a **cost-efficient** way — everything runs on a **single instance** instead of multiple ones.

---

## 📐 Architecture

<img width="1536" height="1024" alt="generated-image" src="https://github.com/user-attachments/assets/79666df7-293d-4126-a621-68e55f27e3dc" />

**Flow:**
- Terraform provisions an EC2 instance.
- On the instance, Docker Compose runs Prometheus, Grafana, and Node Exporter.
- Node Exporter exposes system metrics.
- Prometheus scrapes metrics from Node Exporter.
- Grafana visualizes the collected data from Prometheus.

---

## 🛠️ Tech Stack

- **Terraform** → Infrastructure as Code (IaC) for provisioning AWS EC2  
- **Docker & Docker Compose** → Container orchestration  
- **Prometheus** → Metrics collection and storage  
- **Node Exporter** → System-level metrics exporter  
- **Grafana** → Metrics visualization  

---

## ⚙️ Setup Instructions

### 1. Clone this Repository
```bash
git clone 
cd <your-repo>
