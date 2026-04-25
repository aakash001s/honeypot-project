# 🛡️ Shadow Node — AI-Powered Honeypot System

A full-stack intelligent honeypot that detects, classifies, and analyzes cyber attacks in real time using Machine Learning, dynamic CVSS 3.1 scoring, and a multi-tier AI analysis engine.

---

## 🔍 Overview

Shadow Node simulates a vulnerable system to attract attackers and study their behavior. When an attacker interacts with the decoy login interface, the system:

* Detects attack patterns (SQL Injection, XSS, etc.)
* Classifies threats using ML models
* Dynamically scores severity using CVSS 3.1
* Performs AI-based threat analysis with fallback layers
* Enriches high-risk attacks with real-world threat intelligence
* Logs and stores attack data
* Continuously improves via automated retraining

---

## ⚡ Key Capabilities

* 🧠 **Multi-layer AI Analysis** (GPT → Local LLM → Rule Engine)
* 📊 **Dynamic CVSS 3.1 Scoring** (payload-based, not static)
* 🤖 **Machine Learning Detection** (XGBoost models)
* 🧍 **Behavioral Bot Detection** (mouse, keystroke, timing signals)
* 🌐 **Threat Intelligence Integration** (NVD, CISA KEV, ExploitDB)
* 🔁 **Continuous Learning Pipeline**
* ☁️ **Flexible Logging** (Azure Blob or local)

---

## 🏗️ System Architecture

```
Frontend (Firebase Hosting)
│
├── Decoy Login Page
├── Admin Dashboard (real-time logs)
└── Security Lab

Backend (Flask — Render)
│
├── /api/track
├── /api/analyze
├── /api/stats
└── /health

Core Modules:
├── honeypot/   → Detection + CVSS + logging
├── ml/         → ML models + retraining
├── ai/         → Multi-tier AI engine
├── intel/      → Threat intelligence enrichment
├── fusion/     → Risk scoring engine
└── deception/  → Attack response simulation
```

---

## 🚀 Live Demo

| Role  | Email                                     | Password | Access         |
| ----- | ----------------------------------------- | -------- | -------------- |
| Admin | [admin@gmail.com](mailto:admin@gmail.com) | admin    | Full dashboard |
| User  | [user@gmail.com](mailto:user@gmail.com)   | user     | Security lab   |

⚠️ These credentials are intentionally exposed — this is a honeypot system.

* 🌐 Frontend: [https://ids-3215b.web.app](https://ids-3215b.web.app)
* 🔗 Backend: [https://honeypot-backend-9c81.onrender.com/health](https://honeypot-backend-9c81.onrender.com/health)

---

## ⚙️ Local Setup

### Prerequisites

* Python 3.11+
* pip

### 1. Clone Repository

```bash
git clone https://github.com/aakash001s/honeypot-project.git
cd honeypot-project/backend
```

### 2. Create Virtual Environment

```bash
python -m venv venv
source venv/bin/activate      # Mac/Linux
venv\Scripts\activate         # Windows
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure Environment

```bash
cp .env.example .env
```

### 5. Run Backend

```bash
python app.py
```

Backend runs at:
👉 [http://localhost:5000](http://localhost:5000)

### 6. Run Frontend

```bash
cd ../frontend
python -m http.server 8080
```

---

## 🔑 Environment Variables

| Variable                        | Required | Behavior                   |
| ------------------------------- | -------- | -------------------------- |
| OPENAI_API_KEY                  | No       | Enables GPT-based analysis |
| NVD_API_KEY                     | No       | Enables CVE enrichment     |
| AZURE_STORAGE_CONNECTION_STRING | No       | Enables cloud logging      |
| LOG_STORAGE                     | No       | Defaults to local storage  |

✔ Runs fully offline with rule-based fallback.

---

## 🤖 Machine Learning Models

| Model             | Algorithm        | Input            | Purpose            |
| ----------------- | ---------------- | ---------------- | ------------------ |
| network_model     | XGBoost          | Network features | Detect scans, DDoS |
| web_model         | TF-IDF + XGBoost | Payload text     | Detect SQLi, XSS   |
| behavior_detector | XGBoost          | User behavior    | Bot detection      |

### Retraining

```bash
python train_network_model.py
python ml/web_payload_trainer.py
```

---

## 🧠 AI Analysis Pipeline

```
1. GPT (OpenAI)
      ↓ fallback
2. Local LLM (Ollama/Mistral)
      ↓ fallback
3. Rule-based engine
```

✔ Always functional — even without APIs.

---

## 🔐 Supported Attack Types

| Attack            | Category  | CVSS Range |
| ----------------- | --------- | ---------- |
| SQL Injection     | OWASP A03 | 7.5 – 9.8  |
| XSS               | OWASP A03 | 6.1 – 8.8  |
| Command Injection | OWASP A03 | 8.0 – 9.8  |
| Path Traversal    | OWASP A01 | 5.3 – 7.5  |
| Brute Force       | OWASP A07 | 4.0 – 7.0  |
| Bot Activity      | OWASP A07 | 3.0 – 6.0  |

---

## 📁 Project Structure

```
honeypot-project/
│
├── backend/
│   ├── app.py
│   ├── ai/
│   ├── honeypot/
│   ├── ml/
│   ├── intel/
│   ├── models/
│   └── datasets/
│
├── frontend/
│   ├── index.html
│   ├── security-lab.html
│   ├── admin/dashboard.html
│   └── honeypot-minimal.js
│
├── docs/
└── firebase.json
```

---

## 📊 Highlights

* 🔥 Payload-aware CVSS scoring
* 🧬 Self-improving ML models
* 🕵️ Behavioral fingerprinting system
* 🌍 Real-world threat intelligence mapping
* ⚙️ Offline-first architecture

---

## 🛣️ Roadmap

* [ ] Security BERT model (replace TF-IDF)
* [ ] WebSocket-based live dashboard
* [ ] GeoIP attacker tracking
* [ ] MITRE ATT&CK mapping
* [ ] SIEM integration (Splunk / ELK)
* [ ] Auto firewall blocking

---

## 🧰 Tech Stack

**Backend:** Python, Flask, XGBoost, scikit-learn, pandas
**Frontend:** HTML, CSS, JavaScript, Firebase
**AI:** OpenAI API, Ollama
**Storage:** Azure Blob / Local
**Deployment:** Render + Firebase

---

## 👤 Author

**Aakash**
🔗 [https://github.com/aakash001s](https://github.com/aakash001s)


