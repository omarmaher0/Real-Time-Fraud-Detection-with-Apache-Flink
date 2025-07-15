# Real-Time-Fraud-Detection-with-Apache-Flink
This project demonstrates a simple real-time fraud detection pipeline built using Apache Flink SQL. Instead of using streaming tools like Kafka, the data is ingested from a local JSON file, processed by Flink, and filtered based on suspicious activity (e.g., amount > 200), then written back to an output JSON file.
