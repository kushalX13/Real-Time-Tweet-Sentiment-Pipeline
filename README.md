# 🐦 Streaming Tweet Sentiment Pipeline

An end-to-end **real-time tweet sentiment analysis system** built on **Apache Spark Structured Streaming**, **Delta Lake**, and **MLflow**.  
The pipeline ingests raw tweets, processes them through Bronze → Silver → Gold medallion architecture, applies a **Hugging Face transformer model** for sentiment inference at scale, and logs performance metrics.

---

## 📌 Project Overview
This project demonstrates:
- **Real-time streaming ingestion** of tweets in JSON format.
- **Medallion architecture** (Bronze, Silver, Gold tables) with Delta Lake.
- **Data preprocessing**: timestamp parsing, user mention extraction, text cleaning.
- **Transformer-based sentiment analysis** via MLflow packaged model.
- **Monitoring & visualization** of stream performance in Spark.
- **Exploratory Data Analysis (EDA)** on tweet distributions and user activity.
- **Application-level insights**: aggregated sentiment counts for top mentions.
- **MLflow tracking** for metrics (precision, recall, F1-score) and confusion matrices.

---

## 🛠 Tech Stack
- **Apache Spark Structured Streaming**
- **Delta Lake**
- **Databricks**
- **MLflow**
- **Hugging Face Transformers**
- **Pandas & Matplotlib**

---

## 🚀 Pipeline Workflow

### Bronze (Raw Ingest)
- Ingest raw JSON tweets (date, user, text, sentiment).
- Add `source_file` and `processing_time`.

### Silver (Preprocessing)
- Convert `date → timestamp`.  
- Extract `@mentions`.  
- Remove mentions from text (`cleaned_text`).  

### Gold (Inference)
- Apply Hugging Face Transformer via MLflow UDF.  
- Add `predicted_sentiment`, `predicted_score`, and label IDs.  

### Application Layer
- Aggregate sentiment counts (positive, neutral, negative) per mention.  
- Visualize top 20 mentions by sentiment.  

---

## 📊 Key Features
- **Streaming Orchestration**: Robust handling of micro-batches, schema evolution, and checkpointing.  
- **Performance Monitoring**: Custom loop prints throughput & processing time, with real-time plots.  
- **EDA**: Null checks, user tweet distributions, mentions analysis, top tweeters.  
- **Metrics Tracking**: Precision, Recall, F1-score + Confusion Matrix logged in MLflow.  
- **Optimizations**: Analyzed Spark UI for skew, shuffle, storage, and serialization performance.  

---

## ⚡ Results
- Processed **10,000+ tweets** in structured streaming.  
- Generated **real-time sentiment predictions** at scale.  
- Logged **precision, recall, and F1-score** in MLflow.  
- Visualized top mentions by sentiment (positive = “supporters”, negative = “villains”).  

---

## 📂 Repository Structure
