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

### 3. Broader Goals
- **Proactive Maintenance**: Shift from reactive to real-time predictive maintenance.
- **System Reliability**: Enhance safety and minimize downtime for metro operations.
---

## 📊 **Dataset**  
- **Source**: [MetroPT Dataset](https://archive.ics.uci.edu/dataset/791/metropt+3+dataset).  
- **Volume**: 1,516,948 rows, 17 columns.  
- **Features**: Includes analog sensors (e.g., pressure, temperature, motor current) and digital sensors (e.g., air intake valves, pressure switches).

### Sensor Categories
- **Analog Sensors**: Pressure, temperature, and motor current readings.
- **Digital Sensors**: Electrical signals for air intake valves, pressure switches, and air dryers.

---

## 🛠️ **Technologies Used**  
- **Programming Languages**: Python, PySpark  
- **Libraries**: Pandas, NumPy, Matplotlib, Seaborn, TensorFlow, PySpark MLlib  
- **Machine Learning Models**:  
  - **K-Means Clustering**: For state classification and anomaly detection.  
  - **LSTM Autoencoder**: For time-series anomaly detection.  
  - **Isolation Forest**: For anomaly detection based on isolation principles.  
  - **One-Class SVM**: For identifying anomalies in high-dimensional space (attempted, with challenges).  


---

## 📈 **Methodology**  

### **1. Data Preprocessing**  
- Schema definition for Spark processing.  
- Cleaning minimal data issues and preparing time-series data for analysis.  

### **2. Exploratory Data Analysis (EDA)**  
- **Correlation Heatmaps**: Analyzed sensor relationships (e.g., TP2 and H1 strong negative correlation).  
- **Temporal Trends**: Studied patterns in motor current, oil temperature, and other sensors to identify key trends.  

### **3. Clustering for Anomaly Detection**  
- **K-Means Clustering**: Unsupervised learning for detecting patterns in unlabeled data.
  - **Cluster 0**: Normal operations (~95%)
  - **Cluster 1**: Anomalies (~5%) with high oil temperatures (>70°C) and motor currents (>9A).

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
## References
1. **Davari, Narjes, et al.** "Predictive Maintenance Based on Anomaly Detection Using Deep Learning for Air Production Unit in the Railway Industry." *2021 IEEE 8th International Conference on Data Science and Advanced Analytics (DSAA)*, IEEE, 2021, pp. 1-10. DOI: [10.1109/DSAA53316.2021.9564181](https://doi.org/10.1109/DSAA53316.2021.9564181).

2. **Veloso, Bruno, et al.** "The MetroPT Dataset for Predictive Maintenance." *Scientific Data*, vol. 9, no. 1, 2022, p. 764. DOI: [10.1038/s41597-022-01877-3](https://doi.org/10.1038/s41597-022-01877-3).

3. **Barros, Mário, et al.** "Failure Detection of an Air Production Unit in the Operational Context." *IoT Streams for Data-Driven Predictive Maintenance and IoT, Edge, and Mobile for Embedded Machine Learning*, Springer, 2020, pp. 61-74. DOI: [10.1007/978-3-030-66770-2_5](https://doi.org/10.1007/978-3-030-66770-2_5).

4. **Apache Spark.** "Spark SQL, DataFrames, and Datasets Guide." *Apache Spark*, 2024. [Spark SQL Guide](https://spark.apache.org/docs/latest/sql-programming-guide.html)

---

