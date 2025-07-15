🚨 Real-Time Fraud Detection with Apache Flink (Filesystem Source)
📌 Description
This project demonstrates a simple real-time fraud detection pipeline built using Apache Flink SQL.
Instead of using streaming tools like Kafka, the data is ingested from a local JSON file, processed by Flink, and filtered based on suspicious activity (e.g., amount > 200), then written back to an output JSON file.

📁 Project Structure
bash
Copy
Edit
.
├── data/
│   ├── input/transactions.json   # Input JSON file with raw transactions
│   └── output/fraud.json         # Output JSON file with flagged frauds
├── settings/                     # Flink SQL DDL files (table creation)
├── plugins/                      # Flink connectors (e.g., Kafka jar, if needed later)
├── sql-client/                   # Custom Dockerfile for Flink SQL Client
├── docker-compose.yml            # All services defined here
└── README.md                     # You are here ✅
⚙️ Tools & Technologies
Apache Flink 1.17.1

Flink SQL Client

Docker Compose

Filesystem Connector

Input/Output in JSON Format

📦 How It Works
Source: JSON file with raw transactions
→ /data/input/transactions.json

Processing Logic:

Cast ts_str to TIMESTAMP

Add WATERMARK

Filter where amount > 200

Sink: Write suspicious transactions
→ /data/output/fraud.json

🚀 How to Run
bash
Copy
Edit
# 1. Clone the project
git clone https://github.com/your-username/flink-fraud-detection-json.git
cd flink-fraud-detection-json

# 2. Start services
docker-compose up --build

# 3. Access Flink SQL CLI
docker exec -it sql-client /opt/flink/bin/sql-client.sh
Then paste the SQL files from settings/ to create the tables and start the pipeline.

🧪 Sample Output
Example output (fraud cases with amount > 200):

css
Copy
Edit
+I[2, 250.0, 2024-07-01T10:01:00]
+I[3, 300.5, 2024-07-01T10:02:30]
⚠️ Issues Faced
Flink connector not found (missing JAR)

Timestamp parsing errors

Output file not writing due to path mismatch

File permission issues with mounted volumes

🧩 Future Improvements
Add Kafka as streaming source

Integrate with Schema Registry

Connect to BigQuery or MongoDB

Add unit tests with mock streams

Implement alerting or dashboards (Grafana)

🙌 Author
Omar Maher
Connect on LinkedIn | GitHub: [@your-handle]

