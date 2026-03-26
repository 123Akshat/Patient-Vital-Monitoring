# 🏥 Patient Vital Monitoring System — Real-Time GCP Data Pipeline

![GCP](https://img.shields.io/badge/Google_Cloud-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Apache Beam](https://img.shields.io/badge/Apache_Beam-FF6600?style=for-the-badge&logo=apache&logoColor=white)
![BigQuery](https://img.shields.io/badge/BigQuery-669DF6?style=for-the-badge&logo=googlebigquery&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)

---

## 📌 Project Overview

A fully automated, **end-to-end real-time data engineering pipeline** built on **Google Cloud Platform** that streams live patient vitals, heart rate, SpO₂, and body temperature and delivers live healthcare analytics through a Power BI dashboard.

---

## 🏗️ Architecture

```
Data Source → Pub/Sub (Streaming) → Dataflow + Apache Beam (Processing)
           → BigQuery [Bronze → Silver → Gold] → Power BI (Dashboard)
```
<img width="358" height="178" alt="Picture2" src="https://github.com/user-attachments/assets/7eefd5e3-4e52-4019-aa30-3226cab7c080" />

> **Medallion Architecture** is used across three BigQuery layers:
> - 🥉 **Bronze** — Raw ingested data
> - 🥈 **Silver** — Cleaned & validated data
> - 🥇 **Gold** — Business-ready aggregated data

---

## ⚙️ Tech Stack

| Layer | Technology |
|---|---|
| Cloud Platform | Google Cloud Platform (GCP) |
| Data Streaming | Google Pub/Sub |
| Stream Processing | Apache Beam + Google Dataflow |
| Data Warehouse | Google BigQuery |
| Storage | Google Cloud Storage (Bronze / Silver / Staging) |
| Visualization | Power BI |
| Language | Python |
| Version Control | Git + GitHub |

---

## 🔄 Pipeline Flow

1. **Data Ingestion** — A Python script simulates patient vitals and publishes messages to a **Pub/Sub topic** (`patient_vitals_stream`) in real time
2. **Stream Processing** — **Apache Beam** running on **Google Dataflow** subscribes to the Pub/Sub topic, cleans and transforms the data
3. **Medallion Storage** — Processed data is written to **BigQuery** across three layers (Bronze → Silver → Gold) and staged in **GCS buckets**
4. **Visualization** — **Power BI** connects live to BigQuery's Gold layer to display real-time patient dashboards

---

## 📊 Power BI Dashboard

The live dashboard tracks per-patient metrics in real time:

- 🫀 **Heart Rate AVG**
- 🩸 **SpO₂ AVG**
- 🌡️ **Temperature AVG**
- ⚠️ **Risk Level** (Low / Moderate / High)

<img width="380" height="224" alt="Picture3" src="https://github.com/user-attachments/assets/3758d85c-235e-4fa6-ad50-887811acd87a" />

---

## ☁️ GCP Services Used

- **Pub/Sub** — Messaging backbone for real-time event streaming
- **Dataflow** — Managed runner for Apache Beam jobs
- **BigQuery** — Serverless data warehouse for all pipeline layers
- **Cloud Storage** — Staging buckets for Bronze, Silver, and Staging layers
- **Cloud Shell** — Used for deployment and job management

---

## 🚀 How to Run

### Prerequisites
- GCP account with billing enabled
- Python 3.8+
- GCP SDK installed and authenticated

---

## 📁 Project Structure

```
Patient-Vital-Monitoring-GCP/
│
├── publisher.py              # Simulates & publishes patient vitals to Pub/Sub
├── dataflow_pipeline.py      # Apache Beam pipeline (Dataflow runner)
├── requirements.txt          # Python dependencies
├── architecture.png          # Pipeline architecture diagram
├── dashboard.png             # Power BI dashboard screenshot
└── README.md                 # Project documentation
```

---

## 💡 Key Learnings

- ✅ Real-time streaming data ingestion using **Pub/Sub**
- ✅ Stream processing and transformations with **Apache Beam on Dataflow**
- ✅ Multi-layer data architecture using **Medallion (Bronze/Silver/Gold)**
- ✅ Scalable cloud data warehousing with **BigQuery**
- ✅ Real-time visualization in **Power BI**
- ✅ Fully automated, event-driven pipeline — **zero manual triggers**
- ✅ Deploying and monitoring streaming jobs via **GCP Console**

