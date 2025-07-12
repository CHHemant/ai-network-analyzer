# AI-Based Network Traffic Analyzer

## Overview

The AI-Based Network Traffic Analyzer is a cybersecurity solution that leverages machine learning to analyze network traffic and detect threats such as port scans, denial-of-service attacks, and data exfiltration. It automates traffic inspection, reporting, and alerting, helping organizations proactively defend their networks.

---

## Features

- **Traffic Capture**: Collects network packets using Scapy and saves them for analysis.
- **Feature Engineering**: Extracts and transforms packet data (IP, port, protocol, length) for ML use.
- **Machine Learning Detection**: Trains a Random Forest classifier to distinguish benign from malicious traffic using labeled datasets.
- **Real-Time & Batch Analysis**: Supports both live packet monitoring and analysis of saved `.pcap` or `.csv` files.
- **Alerting & Reporting**: Flags suspicious packets/sessions and compiles actionable alerts into a report.

---

## How It Works

1. **Data Capture**: Use Scapy to sniff packets or import traffic logs.
2. **Preprocessing**: Parse raw traffic to extract features (IP, port, protocol, packet length).
3. **Model Training**: Train a Random Forest model using labeled traffic data.
4. **Detection**: Analyze new traffic; the model flags suspicious activity.
5. **Reporting**: Generate an alert file listing all flagged traffic.

---

## Why Use This Tool?

- Detects threats early, reducing risk and damage.
- Automates network security, saving time and effort.
- Extensible for new protocols, features, and models.
- Real-world, hands-on cybersecurity and ML integration.
- Can be adapted for large-scale enterprise or personal use.

---

## Installation

1. Clone the repo:
   ```bash
   git clone https://github.com/CHHemant/ai-network-analyzer.git
   cd ai-network-analyzer
   ```
2. Install requirements:
   ```bash
   pip install -r requirements.txt
   ```

---

## Usage

**Batch Analysis Example:**
```bash
python src/preprocess.py --input data/sample_traffic.csv --output data/features.csv
python src/train_model.py --input data/features.csv --model data/model.pkl
python src/detect.py --model data/model.pkl --input data/new_traffic.csv --output data/alerts.csv
```

**Real-Time Capture Example:**
```bash
sudo python src/capture.py
# Then preprocess and detect as above
```

---

## Project Structure

```
ai-network-analyzer/
├── README.md
├── requirements.txt
├── data/
│   ├── sample_traffic.csv
│   ├── features.csv
│   ├── model.pkl
│   ├── alerts.csv
├── src/
│   ├── capture.py
│   ├── preprocess.py
│   ├── train_model.py
│   ├── detect.py
│   └── utils.py
├── test/
│   └── test_analyzer.py
└── .gitignore
```

---

## Data & Model

- Use public datasets (UNSW-NB15, CICIDS 2017) or capture your own with Wireshark/Scapy.
- Label traffic: `0` for benign, `1` for malicious.
- Model: Random Forest (modifiable for other algorithms).

---

## Extending the Project

- Add more sophisticated features (timing, DNS, TLS, etc.).
- Use unsupervised or deep learning for anomaly detection.
- Integrate with SIEM or enterprise alerting.

---

## Security & Privacy

- Ensure you have permission to capture network traffic.
- Handle sensitive data according to policy and regulations.

---

## License

MIT License

---

## Support

Open issues or contact the maintainer for help.
