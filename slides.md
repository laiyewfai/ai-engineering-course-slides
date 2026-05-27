---
theme: seriph
title: How to Learn AI Engineering from Scratch & Deploy Locally
info: |
  ## AI Engineering Course
  A structured guide to learning AI Engineering and deploying locally.
class: text-center
drawings:
  persist: false
transition: slide-left
mdc: true
---

# How to Learn AI Engineering
## From Scratch & Deploy Locally

<div class="pt-12">
  <span class="text-xl opacity-50">A structured, project-based guide</span>
</div>

---
layout: center
class: text-center
---

# What You'll Learn

<div class="grid grid-cols-3 gap-8 pt-8 text-left max-w-3xl mx-auto">
<div>
  <div class="text-3xl mb-2">🧠</div>
  <h3 class="text-lg font-bold mb-1">Foundations</h3>
  <p class="text-sm opacity-70">Python, Git, CLI, and core ML concepts</p>
</div>
<div>
  <div class="text-3xl mb-2">🛠️</div>
  <h3 class="text-lg font-bold mb-1">Building</h3>
  <p class="text-sm opacity-70">End-to-end projects with deployment</p>
</div>
<div>
  <div class="text-3xl mb-2">🚀</div>
  <h3 class="text-lg font-bold mb-1">Deploying</h3>
  <p class="text-sm opacity-70">Local-first, production-ready systems</p>
</div>
</div>

---
---

# Prerequisites

<div class="grid grid-cols-2 gap-6 pt-4">

<div>
<div class="border-l-4 border-blue-500 pl-4 mb-4">
  <h3 class="text-lg font-bold">Python (Required)</h3>
  <p class="text-sm opacity-70">Functions, classes, decorators, async/await, type hints, virtual environments</p>
</div>
<div class="border-l-4 border-green-500 pl-4 mb-4">
  <h3 class="text-lg font-bold">Git Fundamentals (Required)</h3>
  <p class="text-sm opacity-70">Clone, commit, push, rebase, branches, SSH keys</p>
</div>
<div class="border-l-4 border-purple-500 pl-4 mb-4">
  <h3 class="text-lg font-bold">Command Line (Required)</h3>
  <p class="text-sm opacity-70">Pipes, grep, awk, sed, aliases, shell scripting</p>
</div>
</div>

<div>
<div class="border-l-4 border-orange-500 pl-4 mb-4">
  <h3 class="text-lg font-bold">Docker (Recommended)</h3>
  <p class="text-sm opacity-70">Containers, images, docker-compose, volumes</p>
</div>
<div class="border-l-4 border-red-500 pl-4 mb-4">
  <h3 class="text-lg font-bold">Math Background (Helpful)</h3>
  <p class="text-sm opacity-70">Linear algebra, calculus (gradients), probability basics</p>
</div>
</div>

</div>

---
layout: two-cols
---

# What is AI Engineering?

AI Engineering sits at the intersection of software engineering and machine learning.

- **Not pure research** — you're not writing papers
- **Not pure ML** — you're not just training models
- **You build systems** that use AI as a component

::right::

<div class="pl-8 pt-8">

| ML Engineering | AI Engineering |
|---------------|----------------|
| Focus on models | Focus on systems |
| Training accuracy | Production reliability |
| Research-driven | Product-driven |
| Jupyter notebooks | CI/CD pipelines |

</div>

<div class="text-sm opacity-60 pt-4">
Key responsibilities: model deployment, monitoring, data pipelines, APIs, cost optimization.
</div>

---
---

# Why Local Deployment?

<div class="grid grid-cols-3 gap-4 pt-8">
<div class="p-4 border rounded text-center">
  <div class="text-2xl mb-2">🔒</div>
  <h3 class="font-bold">Privacy</h3>
  <p class="text-sm opacity-70">Sensitive data never leaves your machine</p>
</div>
<div class="p-4 border rounded text-center">
  <div class="text-2xl mb-2">💰</div>
  <h3 class="font-bold">Zero API Costs</h3>
  <p class="text-sm opacity-70">No rate limits, no per-token pricing</p>
</div>
<div class="p-4 border rounded text-center">
  <div class="text-2xl mb-2">⚡</div>
  <h3 class="font-bold">Free Iteration</h3>
  <p class="text-sm opacity-70">Experiment freely, learn faster</p>
</div>
</div>

<div class="pt-6">

**The payoff:** Build portfolio projects that run entirely on your machine — no cloud bills, no API keys, full control.

</div>

---
---

# Learning Path: Phase 1 — Foundations (Weeks 1–4)

<div class="grid grid-cols-2 gap-6 pt-4">

<div>

### Weeks 1–2: Python Deep Dive

- Advanced Python patterns
- Data structures & algorithms
- Error handling & logging
- Testing with pytest
- Type hints & mypy

</div>

<div>

### Weeks 3–4: Data Science Basics

- Pandas mastery (groupby, merge, pivot)
- Data cleaning & preprocessing
- Exploratory data analysis
- Visualization (Matplotlib, Seaborn)
- NumPy for numerical computing

</div>

</div>

<div class="mt-6 p-4 bg-blue-500/10 rounded text-sm">
  <b>Milestone:</b> Clean a messy dataset and produce an analysis notebook with clear visualizations.
</div>

---
---

# Learning Path: Phase 2 — ML Basics (Weeks 5–8)

<div class="grid grid-cols-2 gap-6 pt-4">

<div>

### Weeks 5–6: Scikit-learn

- Supervised vs unsupervised learning
- Train/test split & cross-validation
- Feature engineering & selection
- Model evaluation metrics
- Pipelines & column transformers

```python
from sklearn.pipeline import Pipeline
from sklearn.ensemble import RandomForestClassifier

pipe = Pipeline([
    ('scaler', StandardScaler()),
    ('clf', RandomForestClassifier())
])
pipe.fit(X_train, y_train)
```

</div>

<div>

### Weeks 7–8: Deep Learning with PyTorch

- Tensors, autograd, and GPU compute
- Building neural networks from scratch
- Training loops & optimizers
- Transfer learning with pretrained models

```python
import torch.nn as nn

class SimpleNet(nn.Module):
    def __init__(self):
        super().__init__()
        self.fc = nn.Sequential(
            nn.Linear(784, 128),
            nn.ReLU(),
            nn.Linear(128, 10)
        )
    def forward(self, x):
        return self.fc(x)
```

</div>

</div>

---
---

# Learning Path: Phase 3 — ML Engineering (Weeks 9–16)

<div class="grid grid-cols-2 gap-6 pt-4">

<div>

### Weeks 9–12: Model Serving

```python
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()

class PredictionRequest(BaseModel):
    text: str

@app.post("/predict")
async def predict(req: PredictionRequest):
    result = model.predict(req.text)
    return {"prediction": result}
```

- FastAPI for REST APIs
- Pydantic for validation
- Async endpoints for throughput
- Docker containerization

</div>

<div>

### Weeks 13–16: MLOps Intro

```bash
# Experiment tracking
mlflow server --host 0.0.0.0 --port 5000

# Data versioning
dvc init
dvc add data/training.csv
dvc push

# Model registry
mlflow models serve -m runs:/<run_id>/model
```

- MLflow for experiment tracking
- DVC for data versioning
- CI/CD for ML pipelines
- A/B testing basics

</div>

</div>

---
---

# Learning Path: Phase 4 — Production (Weeks 17–20+)

<div class="pt-4">

- **Kubernetes basics** — pods, services, deployments, ingress
- **Model monitoring** — data drift, concept drift, prediction latency
- **Scaling strategies** — horizontal pod autoscaling, batching, caching
- **Cost optimization** — spot instances, model quantization, request pooling

<div class="mt-8 p-4 bg-green-500/10 border border-green-500/30 rounded">

### The Goal at 20 Weeks

You can independently:
- Train, evaluate, and serve ML models
- Build containerized AI applications
- Set up monitoring and CI/CD
- Debug production issues
- Optimize for cost and latency

</div>

</div>

---
---

# Essential Tools Stack

<div class="grid grid-cols-2 gap-6 pt-4">

<div>

### Core Libraries
```bash
# ML & Deep Learning
pip install torch scikit-learn pandas numpy
pip install transformers diffusers accelerate

# MLOps
pip install mlflow dvc wandb

# Serving
pip install fastapi uvicorn gunicorn
```

### Development Environment
- VS Code + Python extensions
- Poetry or pip-tools for dependencies
- Jupyter for exploration
- pre-commit hooks for code quality

</div>

<div>

### Containerization

```dockerfile
# Dockerfile
FROM python:3.11-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
```

```yaml
# docker-compose.yml
services:
  app:
    build: .
    ports: ["8000:8000"]
  postgres:
    image: postgres:15
    environment:
      POSTGRES_PASSWORD: secret
```

</div>

</div>

---
---

# Local Deployment Setup

<div class="pt-4">

## Three Tiers of Local Deployment

<div class="grid grid-cols-3 gap-4 pt-4">

<div class="border rounded p-4">

### Tier 1: CPU Only

```bash
docker run -p 8000:8000 \
  -v "$(pwd)/models":/models \
  my-model:latest
```

- Works on any machine
- Good for small models
- FastAPI + ONNX Runtime

</div>

<div class="border rounded p-4">

### Tier 2: GPU Accelerated

```bash
docker run --gpus all \
  -p 8000:8000 \
  --shm-size=8g \
  my-model:latest
```

- NVIDIA GPU required
- CUDA + cuDNN
- vLLM / TorchServe

</div>

<div class="border rounded p-4">

### Tier 3: Full Local Stack

```bash
docker compose up -d
```

- Ollama (LLM serving)
- Chroma (vector DB)
- Open WebUI (chat interface)
- MLflow (experiment tracking)

</div>

</div>
</div>

---
---

# Model Serving Options

<div class="grid grid-cols-2 gap-6 pt-4">

<div>

### HuggingFace Pipelines
```python
from transformers import pipeline

# Zero-code inference
classifier = pipeline("sentiment-analysis")
result = classifier("This is great!")
# [{'label': 'POSITIVE', 'score': 0.99}]

# Any task, any model
generator = pipeline("text-generation", model="gpt2")
summarizer = pipeline("summarization")
```

</div>

<div>

### vLLM for LLMs
```bash
# High-throughput LLM serving
python -m vllm.entrypoints.api_server \
  --model meta-llama/Llama-2-7b \
  --port 8000 \
  --tensor-parallel-size 1

# Features:
# - PagedAttention for efficiency
# - Continuous batching
# - OpenAI-compatible API
```

### Ollama (Simplest)
```bash
ollama pull llama3.2:3b
ollama serve
# OpenAI-compatible at localhost:11434
```

</div>

</div>

---
---

# Monitoring & Observability

<div class="grid grid-cols-2 gap-6 pt-4">

<div>

### What to Monitor

- **Request latency** — p50, p95, p99
- **Throughput** — requests per second
- **Error rates** — 4xx, 5xx breakdown
- **Model metrics** — prediction distribution, confidence scores
- **Data drift** — input feature shifts over time
- **Resource usage** — CPU, GPU, memory

</div>

<div>

### Tools

**Cloud / Managed:**
- LangSmith — LLM tracing & eval
- Arize — ML observability
- Weights & Biases — experiment tracking

**Self-Hosted:**
- Prometheus + Grafana — metrics & dashboards
- Structured logging (JSON format)
- Health check endpoints (`/health`, `/ready`)

</div>

</div>

---
---

# Portfolio Projects to Build

<div class="pt-2">

<div class="grid grid-cols-2 gap-6">

<div>

### Starter

**1. Image Classifier API**
- CIFAR-10 with ResNet-18
- FastAPI endpoint
- Docker deployment
- ~2 weeks

**2. Sentiment Analysis Service**
- HuggingFace transformers
- Batch prediction support
- Request validation
- ~1 week

</div>

<div>

### Intermediate

**3. Document Q&A (RAG)**
- LangChain + Chroma/Faiss
- PDF ingestion pipeline
- Streaming responses
- ~3 weeks

**4. Time Series Forecaster**
- LSTM or Prophet model
- Historical query API
- Scheduled retraining
- ~3 weeks

</div>

</div>

<div class="mt-4">

### Advanced

<div class="grid grid-cols-2 gap-4 pt-2">
<div class="border rounded p-3">

**5. Multi-Model Router** — Ensemble predictions, model routing, rate limiting, auth

</div>
<div class="border rounded p-3">

**6. End-to-End ML Platform** — Data pipeline, training jobs, experiment tracking, model registry, CI/CD

</div>
</div>

</div>

</div>

---
---

# Project Structure Template

<div class="pt-4">

```
project/
├── app/
│   ├── __init__.py
│   ├── main.py              # FastAPI entry point
│   ├── models/
│   │   ├── __init__.py
│   │   └── classifier.py    # Model loading & inference
│   └── api/
│       ├── __init__.py
│       └── routes.py        # API endpoints
├── data/
│   ├── raw/                 # Original data
│   └── processed/           # Cleaned data
├── notebooks/               # Exploration & analysis
├── docker/
│   ├── Dockerfile
│   └── docker-compose.yml
├── tests/
│   ├── test_api.py
│   └── test_model.py
├── configs/                 # Model & training configs
├── README.md
├── requirements.txt
└── .gitignore
```

</div>

---
layout: center
class: text-center
---

# Learning Resources

<div class="grid grid-cols-3 gap-6 pt-8 text-left max-w-3xl mx-auto">

<div>

### Free Courses
- **fast.ai** — Practical Deep Learning
- **Kaggle Learn** — ML micro-courses
- **Google ML Crash Course**
- **DeepLearning.AI Short Courses**

</div>

<div>

### Books
- *Designing Machine Learning Systems* (Chip Huyen)
- *Machine Learning Engineering* (Andriy Burkov)
- *Building Machine Learning Pipelines* (Hapke & Nelson)

</div>

<div>

### Communities
- **r/MachineLearning**
- **r/LocalLLaMA**
- **HuggingFace Discord**
- **Kaggle Discussions**

</div>

</div>

---
---

# Your Action Plan

<div class="grid grid-cols-3 gap-4 pt-4">

<div class="border rounded p-4">

### Weeks 1–2
- Set up dev environment
- Complete Python deep dive
- Build first data pipeline
- Start a GitHub project

</div>

<div class="border rounded p-4">

### Weeks 3–4
- Master Pandas & NumPy
- Train first ML model
- Deploy locally with Docker
- Publish your first project

</div>

<div class="border rounded p-4">

### Weeks 5–8+
- Add monitoring & logging
- Build second project
- Share on LinkedIn/GitHub
- Join AI engineering communities

</div>

</div>

<div class="mt-6">

```bash
# Quick start — install the essentials right now
python -m pip install torch pandas scikit-learn fastapi uvicorn
python -m pip install mlflow dvc wandb
docker run -it --rm -p 8000:8000 my-ai-model
```

</div>

---
layout: center
class: text-center
---

# Key Takeaways

<div class="grid grid-cols-3 gap-8 pt-8 text-left max-w-3xl mx-auto">
<div>
  <div class="text-3xl mb-2">🎯</div>
  <h3 class="text-lg font-bold mb-1">Start with Fundamentals</h3>
  <p class="text-sm opacity-70">Python, Git, CLI — these pay dividends forever</p>
</div>
<div>
  <div class="text-3xl mb-2">📚</div>
  <h3 class="text-lg font-bold mb-1">Follow a Structure</h3>
  <p class="text-sm opacity-70">Phased learning beats random tutorial hopping</p>
</div>
<div>
  <div class="text-3xl mb-2">📦</div>
  <h3 class="text-lg font-bold mb-1">Build & Ship</h3>
  <p class="text-sm opacity-70">Portfolio projects are your best resume</p>
</div>
</div>

<div class="grid grid-cols-2 gap-8 pt-6 text-left max-w-2xl mx-auto">
<div>
  <div class="text-3xl mb-2">🛠️</div>
  <h3 class="text-lg font-bold mb-1">Master the Tools</h3>
  <p class="text-sm opacity-70">Docker, FastAPI, MLOps — the engineer's toolkit</p>
</div>
<div>
  <div class="text-3xl mb-2">🚀</div>
  <h3 class="text-lg font-bold mb-1">Deploy Locally First</h3>
  <p class="text-sm opacity-70">Learn without bills, scale when you're ready</p>
</div>
</div>

---
layout: center
class: text-center
---

# Thank You!

<div class="pt-8">

## Let's Build Together

<div class="pt-4 opacity-50">
  Start small. Ship fast. Iterate in public.
</div>

<div class="pt-12 text-sm opacity-30">
  Press Esc for overview · Made with Slidev
</div>

</div>
