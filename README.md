# 🛫 LogAnalyzer for Anomaly Detection in Autonomous Drones

[![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)](https://www.python.org/)  
[![Confidential](https://img.shields.io/badge/Confidential-Leonardo-red)](https://www.leonardo.com)

Hybrid multi-layer anomaly detection from PX4 telemetry data, combining rule-based expert systems, unsupervised outlier detection, and supervised learning capabilities.

---

## 🧠 About the Project

**LogAnalyzer** is an advanced system designed to detect anomalies in the behavior of **autonomous drones** based on telemetry data collected from **PX4** autopilot logs.

The project integrates three layers of anomaly detection to ensure both **structured, interpretable analysis** and **adaptive outlier identification**:

- 🧩 **Rule-Based Detection** — structured knowledge through expert-defined conditions
- 🧪 **Unsupervised Detection** — machine learning and statistical analysis for unknown patterns
- 🧠 **Supervised Detection** *(future work)* — classification based on labelled anomaly data

The system supports both **offline log analysis** and **real-time telemetry streaming** (currently in development), with a strong focus on modularity, extensibility, and robustness to varying drone configurations.

This project is developed within the **MSc Thesis in Automation Engineering** at the **University of Bologna**, in collaboration with **Leonardo S.p.A.**.

> 📜 **Confidentiality Notice**:  
> The project and its source code are property of **Leonardo S.p.A.** and are intended for internal and confidential use only.

---

## 🏗 System Architecture

LogAnalyzer is structured into a **layered architecture**, composed of:

- 🔹 **Rule-Based Layer**:  
  Apply expert-defined rules, thresholds, and logical conditions, stored in modular YAML files, over PX4 telemetry topics.

- 🔹 **Unsupervised Outlier Layer**:  
  Extract structured CSV datasets from PX4 logs, preprocess data, and apply outlier detection methods (Z-Score, IQR, Isolation Forest, multivariate analysis).

- 🔹 **Supervised Learning Layer** *(Planned)*:  
  Train supervised models on labelled datasets to automatically classify and flag anomalies with high precision.

The architecture ensures **scalability**, **resilience to missing data**, and **adaptability** across different drone types.

---

## 🗂 Project Structure

```
📦 loganalyzer/
├── 📁 rules/               # YAML files defining detection rules
├── 📁 log_parser/           # PX4 ULog parsing and CSV extraction
├── 📁 outlier_detection/    # Statistical and ML-based outlier detection tools
├── 📁 cli/                  # Terminal interfaces (Textual / questionary)
├── 📁 config/               # Configurations and default parameters (YAML)
├── 📁 utils/                # Shared utilities (normalization, clustering, etc.)
├── 📁 tests/                # Test suite (Pytest)
├── 📁 images/               # Figures and visual outputs (optional)
├── 💻 main.py               # Main entry point for LogAnalyzer
├── 📘 report_master_thesis.pdf # Complete MSc Thesis Report
└── 📄 README.md             # This file
```

---

## ⚙️ How to Run

### 🔹 Offline Analysis

Analyze PX4 `.ulg` log files:

```bash
$ python3 main.py
```

- Navigate via interactive CLI powered by Textual and questionary.
- Select detection method (rule-based, unsupervised, or combined).
- Choose log files from a list or via an optional graphical file picker.
- View and save anomaly detection reports and visualizations.

---

### 🔹 Online Analysis

Stream real-time PX4 telemetry data and analyze on-the-fly:

```bash
$ python3 main.py --mode online
```

---

## 🧰 Key Features

### ▶ Rule-Based Anomaly Detection

- Human-defined YAML rules: thresholds, conditions, and logical relations.
- Automatic parsing and runtime evaluation on PX4 topics.
- Temporal and topic-based clustering of detected anomalies.
- Generation of structured, interpretable anomaly logs.

### ▶ Unsupervised Outlier Detection

- Parse PX4 telemetry into structured CSV format.
- Data preprocessing:
  - Manage missing topic data
  - Normalize numerical features
  - Remove non-numerical fields
- Apply multiple anomaly detection methods:
  - Z-Score analysis
  - Interquartile Range (IQR)
  - Isolation Forest
  - Multivariate statistical methods
- Produce detailed CSV reports and visual outputs.

### ▶ CLI and User Interface

- Interactive command-line interface based on Textual.
- Keyboard navigation with highlighted menu selections.
- Optional fallback to graphical file selection for ease of use.
- Streamlined selection of detection type and input data.

### ▶ Supervised Learning

- Collection of ground-truth labelled anomaly datasets.
- Training of classifiers (e.g., Random Forests, SVMs).
- Integration with multi-layer detection for dynamic feedback.

---

## 📊 Output and Evaluation

- 📄 Anomaly reports grouped by time window and telemetry topic.
- 📈 Outlier visualizations and cluster density plots.
- 🛫 Full support for multiple drone platforms and configurations.
- 🔄 Robust error handling in presence of missing data or incomplete topics.

---

## 🚀 Roadmap

- Full implementation of real-time anomaly detection from telemetry streams.
- Expansion of expert rulebase through semi-automated rule learning.
- Deployment of supervised anomaly classifiers.
- Integration with MAVLink live telemetry.
- Enhanced Textual-based GUI for configuration and results viewing.

---

## 👨‍🎓 Author

**MSc Thesis in Automation Engineering**, University of Bologna

- Andrea Perna 📧 and.perna99@gmail.com

---

## 👩‍🏫 Supervisors

- Prof. Giuseppe Notarstefano
- Dr. Alice Rosetti
- Dr. Fabrizio Schiano
- Dr. Michele Marolla

---

## 📎 Resources

- 📘 MSc Thesis Report (PDF) *(Confidential)*
- 📄 Anomaly Reports (Optional)

---

## 📜 License

All rights reserved. Internal and confidential use only.  
Property of **Leonardo S.p.A.**.

---
