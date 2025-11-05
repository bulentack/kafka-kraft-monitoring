# 📡 Kafka KRaft Monitoring Stack

This repository demonstrates a **Kafka cluster in KRaft mode** (no ZooKeeper) deployed via **Helm**, integrated with **Prometheus** for metrics and **Grafana** for visualization.

---

## 🧱 Architecture

---

## ⚙️ Prerequisites
- Kubernetes cluster (minikube, k3s, OKE, etc.)
- Helm ≥ 3.8
- Prometheus Operator installed
- Grafana instance accessible

---

## 🪜 Deployment Steps
```bash
git clone https://github.com/bulentack/kafka-kraft-monitoring
cd kafka-kraft-monitoring

# Install Kafka in KRaft mode
helm install kafka oci://registry-1.docker.io/bitnamicharts/kafka -f values-kraft.yaml -n kafka --create-namespace

# Apply Prometheus ServiceMonitor
kubectl apply -f prometheus.yaml -n kafka


📊 Grafana Dashboard Import

Open Grafana → Dashboards → Import

Upload grafana-dashboard.json

Select Prometheus data source

You’ll see metrics for:

Messages in/out per second

Bytes throughput

Broker-level and topic-level statistics


🧰 Stack

Kafka • KRaft • Helm • Prometheus • Grafana • Kubernetes





