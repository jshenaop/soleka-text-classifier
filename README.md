# Soleka — Text Classifier

> Automated topic categorization of regulatory submissions using probabilistic NLP.  
> Built for the **Communications Regulation Commission of Colombia (CRC)**.

![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=flat-square&logo=python&logoColor=white)
![License](https://img.shields.io/badge/License-Apache%202.0-D22128?style=flat-square&logo=apache&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![Status](https://img.shields.io/badge/Status-Portfolio%20Project-6C3483?style=flat-square)
![Domain](https://img.shields.io/badge/Domain-RegTech-6C3483?style=flat-square)
![NLP](https://img.shields.io/badge/NLP-Text%20Classification-0078D4?style=flat-square)
![Built For](https://img.shields.io/badge/Built%20for-CRC%20Colombia-FFCD00?style=flat-square&logoColor=black)

---

## Overview

**Soleka** is a Python-based text classification API designed to automate the routing and categorization of mobile device **homologation requests** — official regulatory submissions that telecom manufacturers must file to certify devices for the Colombian market.

Instead of manually triaging hundreds of documents, Soleka applies a **Naive Bayes classifier** trained on regulatory text to predict the procedural category of each submission. This reduces processing time, standardizes categorization, and creates a scalable foundation for more advanced NLP pipelines.

---

## Problem

The CRC receives a continuous flow of regulatory documents. Manually reading and categorizing each request is time-consuming and error-prone. A single misclassification can delay device certifications and create friction for manufacturers.

Soleka addresses this by treating document triage as a text classification problem — automating what was previously a human bottleneck.

---

## Features

- `POST /predict` — Submit text and receive a predicted regulatory category (homologación or not)
- `POST /demographics` — Gender and age prediction from text input
- Naive Bayes probabilistic classification
- Decision Tree and Deep Learning models (analytics module)
- Token-based user authentication
- Connection to production regulatory databases

---

## Tech Stack

| Layer | Technology |
|---|---|
| Language | Python 3 |
| ML / NLP | scikit-learn (Naive Bayes, Decision Tree) |
| API | REST (POST endpoints) |
| Auth | Token-based authentication |
| Frontend | HTML templates |
| License | Apache 2.0 |

---

## Project Structure

```
soleka-text-classifier/
├── soleka.py            # Main application entry point
├── models.py            # ML model definitions and training logic
├── config.py            # Configuration and environment settings
├── analytics/           # Experimental model comparisons (NB, DT, Deep Learning)
├── resources_v1/        # Training data and regulatory document resources
├── templates/           # HTML templates for the interface
└── instructions.txt     # Setup and usage notes
```

---

## Quickstart

```bash
# Clone the repository
git clone https://github.com/jshenaop/soleka-text-classifier.git
cd soleka-text-classifier

# Install dependencies
pip install -r requirements.txt

# Run the app
python soleka.py
```

Then send a POST request with your regulatory text:

```bash
curl -X POST http://localhost:5000/predict \
  -H "Content-Type: application/json" \
  -d '{"text": "Solicitud de homologación para dispositivo móvil marca Samsung..."}'
```

---

## Models

Soleka was designed with a multi-model analytics layer to compare approaches:

- **Naive Bayes** — Fast, probabilistic baseline. Well-suited for sparse regulatory text.
- **Decision Tree** — Interpretable rule-based classification.
- **Deep Learning** — Experimental neural approach for future versions.

---

## Roadmap

**Version 1 (current)**
- [x] Topic classification for homologación requests
- [x] Demographics prediction endpoint
- [x] Real database integration
- [x] User and token authentication

**Version 2 (planned)**
- [ ] Multi-label classification across all CRC procedural categories
- [ ] Active learning pipeline to improve with new submissions
- [ ] Dashboard for classification analytics

---

## Context

This project was built as a **RegTech tool for public sector efficiency** — applying NLP to reduce operational overhead in a government regulatory body. It demonstrates how probabilistic text classification can be practically deployed in Spanish-language institutional contexts.

---

## Author

**Juan Sebastián Henao**  
[jshenaop@gmail.com](mailto:jshenaop@gmail.com)  
[github.com/jshenaop](https://github.com/jshenaop)

---

## License

Distributed under the [Apache 2.0 License](LICENSE).

**SOLEKA - Version 2**

(Waiting for ideas)


