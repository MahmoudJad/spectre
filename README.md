# Spectre

Spectre is a lightweight, containerized data pipeline designed to collect, transform, and index logs into OpenSearch.  
Powered by **Fluentd**, **OpenSearch**, and **Docker**, Spectre acts as the invisible force that reveals insights hidden within system events.

---

## 🚀 Features

- **Log Collection via Fluentd**  
  Aggregates logs from multiple sources, containers, and services.

- **Real-time Indexing into OpenSearch**  
  Streams data directly into an OpenSearch index for fast search and analytics.

- **Scripted Index Population**  
  A built-in script allows you to bootstrap or refresh OpenSearch indices with default or custom data.

- **Fully Containerized**  
  Easy to deploy locally or in CI/CD pipelines using Docker or Docker Compose.

- **Modular & Extensible**  
  Add new data inputs, filters, or output plugins without breaking the pipeline.

---

## 🧱 Architecture Overview

[Log Sources]
↓
(Fluentd)
↓
[OpenSearch Index]
↓
(Optional Scripts)


Spectre uses Fluentd as the ingestion gateway and OpenSearch as the search engine.  
Additional scripts help pre-populate or manage indices as needed.

---

## 📦 Project Structure

spectre/
├── docker-compose.yml
├── fluent.conf 
│── Dockerfile.fluentd
├── script.ipynb
└── README.md

---

## 🐳 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/MahmoudJad/spectre.git
cd spectre

```

### 2. Start the pipeline

`docker compose up -d`

### 3. Verify OpenSearch status
Open your browser and navigate to:

`http://localhost:9200`

You should see OpenSearch cluster details.

---

### 📝 Populate the Index
Use the built-in script to populate the target index with default data:
`Run the cell in the notebook`

You can customize the script for bulk insertion, schema setup, mappings, or index refresh routines.

---

### ⚙️ Configuration

Fluentd
Modify fluentd/fluent.conf to configure inputs, filters, and outputs.

OpenSearch
Adjust settings, mappings, credentials, or index names inside docker-compose.yml 

---

### 📖 Logs
View Fluentd logs:
`docker logs spectre-fluentd`

View OpenSearch logs:
`docker logs spectre-opensearch`

---

### 🤝 Contributing
Contributions are welcome.
Feel free to open issues or submit PRs for improvements, bug fixes, or new integrations.

### 👁️ About the Name
Inspired by DC’s Spectre, the embodiment of hidden truth and justice.
Spectre reveals what lies beneath — just like this service uncovers insight from raw logs.