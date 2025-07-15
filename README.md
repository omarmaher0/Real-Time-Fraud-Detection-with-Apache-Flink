# 🚨 Real-Time Fraud Detection using Apache Flink (No Kafka)

A clean and minimal **real-time fraud detection pipeline** using **Apache Flink SQL** — powered by **JSON file input/output** and Docker Compose.

---

## 📁 Project Structure

```
.
├── data/
│   ├── input/
│   │   └── transactions.json       # JSON file as source
│   └── output/
│       └── fraud.json              # JSON file as sink
├── settings/                       # SQL DDL files (CREATE TABLE statements)
├── plugins/                        # Optional: for connectors (e.g., Kafka)
│   └── kafka/                      # (future use)
├── sql-client/                     # Custom Dockerfile for Flink SQL CLI
├── docker-compose.yml              # Main Docker orchestration file
└── README.md                       # Project documentation
```

---

## ⚙️ Tech Stack

| Component        | Tool                             |
|------------------|----------------------------------|
| Stream Processor | **Apache Flink** 1.17.1          |
| Query Language   | **Flink SQL**                    |
| Containerization | **Docker Compose**               |
| Format           | **JSON (input & output)**        |
| Connector Used   | **Filesystem**                   |

---

## 🔄 Pipeline Flow

> 📥 **Source** → ⚙️ **Flink SQL Logic** → 📤 **Sink**

```text
[ /data/input/transactions.json ] 
         │
         ▼
[ Filter amount > 200 & Cast timestamp ]
         │
         ▼
[ /data/output/fraud.json ]

---

# 1. Clone the repo
git clone https://github.com/your-username/flink-fraud-detection-json.git
cd flink-fraud-detection-json

# 2. Build & Run
docker-compose up --build

# 3. Open Flink SQL CLI
docker exec -it sql-client /opt/flink/bin/sql-client.sh

---

👤 Author
Omar Oun
📎 LinkedIn: @omaroun
💻 GitHub: @omarmaher0

