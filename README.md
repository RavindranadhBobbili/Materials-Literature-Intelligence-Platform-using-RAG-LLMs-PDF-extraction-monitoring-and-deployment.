# Materials-Literature-Intelligence-Platform-using-RAG-LLMs-PDF-extraction-monitoring-and-deployment.
AeroEngine FatigueGPT is a production-oriented Scientific AI platform designed to predict fatigue behavior of aerospace alloys using literature-derived experimental data, machine learning, Retrieval-Augmented Generation (RAG), and modern LLMOps principles

AeroEngine FatigueGPT
Literature-Driven Fatigue Intelligence Platform for Aerospace Alloys
Overview

AeroEngine FatigueGPT is a production-oriented Scientific AI platform designed to predict fatigue behavior of aerospace alloys using literature-derived experimental data, machine learning, Retrieval-Augmented Generation (RAG), and modern LLMOps principles.

The platform automatically extracts fatigue-related information from research papers and technical reports, builds validated datasets, trains fatigue prediction models, and provides interactive APIs and dashboards for engineers and researchers.

Unlike generic AI assistants, AeroEngine FatigueGPT is specifically focused on fatigue life estimation of aeroengine alloys and demonstrates the convergence of:

Materials Informatics
Scientific Machine Learning
Retrieval-Augmented Generation (RAG)
LLMOps
FastAPI Deployment
Observability and Monitoring
Responsible AI
Motivation

Fatigue failure remains one of the most critical failure mechanisms in aerospace components.

Thousands of fatigue experiments have already been reported in journals, conference proceedings, technical reports, and handbooks.

However:

Most fatigue data remains locked inside PDFs.
Data is difficult to search and reuse.
Experimental knowledge is fragmented across decades of literature.
Engineers repeatedly perform similar experiments because historical data is inaccessible.

AeroEngine FatigueGPT addresses this challenge by transforming literature into an AI-ready fatigue intelligence system.

Problem Statement

Traditional workflow:

Research Paper
      ↓
Human Reading
      ↓
Manual Data Extraction
      ↓
Spreadsheet Creation
      ↓
Fatigue Analysis

AeroEngine FatigueGPT workflow:

Research Paper
      ↓
PDF Extraction
      ↓
Fatigue Data Extraction
      ↓
Validated Dataset
      ↓
Machine Learning
      ↓
Fatigue Intelligence API
Target Materials

The platform currently focuses on aerospace alloys:

Titanium Alloys
Ti-6Al-4V
Ti6242
Ti17
Ti5553
Ti834
Nickel Superalloys
Inconel 718
Inconel 625
RR1000
Waspaloy
Haynes 282
Rene 88DT
Udimet 720
Input Variables

The system supports:

Variable	Description
Stress	Applied cyclic stress
Temperature	Operating temperature
Frequency	Loading frequency
Load Ratio	R ratio
Fracture Toughness	KIC
Alloy Type	Material designation
Environment	Optional service environment
Outputs

The platform predicts:

Fatigue Life
Cycles to Failure
S-N Curves
Stress vs Cycles
Crack Growth
da/dN

using Paris Law

Failure Risk
Probability of Failure
System Architecture
                           AeroEngine FatigueGPT

┌─────────────────────────────────────────────────────────┐
│                   Literature Sources                    │
├─────────────────────────────────────────────────────────┤
│ Research Papers                                         │
│ Technical Reports                                       │
│ Conference Proceedings                                  │
│ Government Reports                                      │
└─────────────────────────────────────────────────────────┘
                          │
                          ▼
┌─────────────────────────────────────────────────────────┐
│                PDF Extraction Engine                    │
├─────────────────────────────────────────────────────────┤
│ PyPDF                                                   │
│ PDFPlumber                                              │
│ OCR Extensions                                          │
└─────────────────────────────────────────────────────────┘
                          │
                          ▼
┌─────────────────────────────────────────────────────────┐
│                Fatigue Data Extraction                  │
├─────────────────────────────────────────────────────────┤
│ Stress                                                  │
│ Temperature                                             │
│ Frequency                                               │
│ Load Ratio                                              │
│ KIC                                                     │
│ Fatigue Life                                            │
└─────────────────────────────────────────────────────────┘
                          │
                          ▼
┌─────────────────────────────────────────────────────────┐
│                   Structured Dataset                    │
└─────────────────────────────────────────────────────────┘
                          │
                          ▼
┌─────────────────────────────────────────────────────────┐
│                   Machine Learning                      │
├─────────────────────────────────────────────────────────┤
│ Random Forest                                           │
│ Gradient Boosting                                       │
│ XGBoost (future)                                        │
│ Physics-Informed ML                                     │
└─────────────────────────────────────────────────────────┘
                          │
                          ▼
┌─────────────────────────────────────────────────────────┐
│                  Fatigue Intelligence API               │
└─────────────────────────────────────────────────────────┘
                          │
                          ▼
┌─────────────────────────────────────────────────────────┐
│                     Dashboard                           │
└─────────────────────────────────────────────────────────┘
Key Features
Literature Intelligence

Automatically extracts fatigue-related information from PDFs.

Extracted Fields
Alloy
Stress
Temperature
Frequency
Load Ratio
KIC
Fatigue Life
Fatigue Life Prediction

Predicts:

Nf

for unseen loading conditions.

S-N Curve Generation

Generates stress-life curves.

Supports:

Basquin Relationship

Future:

Probabilistic S-N Curves
Crack Growth Prediction

Implements:

Paris Law

da/dN = C(ΔK)^m

Used for:

Damage tolerance analysis
Remaining life estimation
Failure Risk Scoring

Calculates:

Low Risk
Medium Risk
High Risk

based on operating conditions.

Monitoring

Tracks:

Metric	Purpose
Latency	API performance
Requests	Usage
Prediction Time	ML inference
Error Rate	Reliability
Technology Stack
Backend
Python
FastAPI
Machine Learning
Scikit-Learn
NumPy
Pandas
Literature Processing
PyPDF
Regex
NLP
Storage
SQLite

Future:

PostgreSQL
Deployment
Docker
Render

Future:

Kubernetes
Installation

Clone repository:

git clone https://github.com/USERNAME/AeroEngine-FatigueGPT.git

cd AeroEngine-FatigueGPT

Create environment:

conda create -n fatiguegpt python=3.10

conda activate fatiguegpt

Install dependencies:

pip install -r requirements.txt
Running Locally
python aeroengine_fatigue_gpt.py

Open:

http://127.0.0.1:8300

Swagger API:

http://127.0.0.1:8300/docs
API Examples
Train Model
POST /train
Predict Fatigue Life
POST /predict

Input:

{
  "alloy":"Inconel 718",
  "stress":650,
  "temperature":650,
  "frequency":20,
  "r_ratio":0.1,
  "kic":75
}

Output:

{
  "fatigue_life_cycles": 120000,
  "failure_probability": 0.21,
  "risk_level":"Medium"
}
Deployment
Docker
docker build -t fatiguegpt .
docker run -p 8300:8300 fatiguegpt
Render

Push repository to GitHub.

Connect Render.

Deploy using:

render.yaml
Future Roadmap
Version 2
OpenAlex integration
Semantic Scholar integration
Automated literature harvesting
Version 3
FAISS vector database
Scientific RAG
Version 4
LLM-powered fatigue assistant
Version 5
Physics-informed neural networks
Version 6
Probabilistic fatigue modeling
Research Impact

Potential applications:

Aeroengine design
Life extension programs
Digital twins
Maintenance scheduling
Materials selection
Certification support
