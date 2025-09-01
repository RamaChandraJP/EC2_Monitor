# 🚀 EC2 Monitoring with Prometheus & Grafana (Terraform + Docker Compose)

This project provisions an **AWS EC2 instance** using **Terraform** and deploys a monitoring stack (**Prometheus, Grafana, Node Exporter**) on it using **Docker Compose**.  
The goal is to monitor the EC2 instance itself in a **cost-efficient** way — everything runs on a **single instance** instead of multiple ones.

---

💰 Cost Optimization

Instead of launching multiple EC2 instances (one each for Prometheus, Grafana, and Node Exporter), this project consolidates everything into a single EC2 instance, reducing AWS costs while still providing full observability.

---

## 📐 Architecture

<img width="600" height="600" alt="generated-image" src="https://github.com/user-attachments/assets/79666df7-293d-4126-a621-68e55f27e3dc" />

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
git clone https://github.com/RamaChandraJP/Monitor.git
apt install -y docker.io && docker-compose
sudo usermod -aG docker ubuntu ##Log out & log back in to apply Docker group changes.
mkdir monitor && cd monitor
docker compose up -d
docker compose logs -f
```

Access the Services
Prometheus → http://<ec2-public-ip>:9090

Grafana → http://<ec2-public-ip>:3000 (default login: admin/admin)

Node Exporter → http://<ec2-public-ip>:9100/metrics

---

📊 Grafana Dashboard

You can import Grafana’s Node Exporter Dashboard (ID: 1860) from the Grafana dashboards library to visualize CPU, Memory, Disk, and Network metrics.

<img width="1899" height="751" alt="image" src="https://github.com/user-attachments/assets/bbd033d0-4f37-429f-ae4e-2c772d3276cc" />


