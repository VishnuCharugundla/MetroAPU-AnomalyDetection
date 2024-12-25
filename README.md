# MetroAPU-AnomalyDetection  

## 🚀 **Project Overview**  
This project focuses on developing an **anomaly detection system** for the **Auxiliary Power Unit (APU)** of metro trains, a critical component that maintains air pressure for systems like braking. Failures in the APU can cause operational disruptions, downtime, and costly repairs. By leveraging **machine learning**, **deep learning**, and **big data analytics**, this project aims to:  
- Detect anomalies in sensor readings.  
- Predict failure risks.  
- Enable **proactive maintenance** to enhance reliability and safety.  

---

## 🎯 **Project Goals**  

### 1. **Prediction Goals**  
- **Anomaly Detection**: Identify abnormal readings in parameters like pressure, temperature, and motor current.  
- **Failure Risk Prediction**: Assign risk scores to high-risk periods, enabling early interventions.  

### 2. **Inference Goals**  
- Analyze **sensor correlations** to detect inefficiencies.  
- Classify operational states (e.g., normal vs. high-load conditions).  
- Conduct temporal analysis to identify patterns of anomalies and optimize maintenance schedules.  

---

## 📊 **Dataset**  
- **Source**: [MetroPT Dataset](https://archive.ics.uci.edu/dataset/791/metropt+3+dataset).  
- **Volume**: 1,516,948 rows, 17 columns.  
- **Features**: Includes analog sensors (e.g., pressure, temperature, motor current) and digital sensors (e.g., air intake valves, pressure switches).  

---

## 🛠️ **Technologies Used**  
- **Programming Languages**: Python, PySpark  
- **Libraries**: Pandas, NumPy, Matplotlib, Seaborn, TensorFlow, PySpark MLlib  
- **Machine Learning Models**:  
  - **K-Means Clustering**: For state classification and anomaly detection.  
  - **LSTM Autoencoder**: For time-series anomaly detection.  

---

## 📈 **Methodology**  

### **1. Data Preprocessing**  
- Schema definition for Spark processing.  
- Cleaning minimal data issues and preparing time-series data for analysis.  

### **2. Exploratory Data Analysis (EDA)**  
- **Correlation Heatmaps**: Analyzed sensor relationships (e.g., TP2 and H1 strong negative correlation).  
- **Temporal Trends**: Studied patterns in motor current, oil temperature, and other sensors to identify key trends.  

### **3. Clustering for Anomaly Detection**  
- Applied **K-Means** with optimal clusters (k=2) to separate normal operations from anomalies.  

### **4. Deep Learning with LSTM Autoencoder**  
- Trained on 10-step sequences to detect anomalies via reconstruction errors.  
- Set thresholds at the 95th percentile to flag outliers.  

---

## 🌟 **Key Results**  
- **Clustering Insights**:  
  - Cluster 0 (95%): Normal operations.  
  - Cluster 1 (5%): Anomalous conditions, e.g., high oil temperatures or motor current.  

- **LSTM Autoencoder**:  
  - Successfully flagged 5% of data points as anomalies.  
  - Reconstruction errors aligned with K-Means results.  

- **Temporal Insights**:  
  - Anomalies peak during early morning hours (2 AM - 5 AM), coinciding with system transitions.  

---

## 🔧 **Challenges**  
- Difficulty integrating **Isolation Forest** and **One-Class SVM** with PySpark.  
- Defining optimal anomaly thresholds using statistical assumptions.  
- Limited labeled data, restricting the use of traditional metrics like precision and recall.  

---

