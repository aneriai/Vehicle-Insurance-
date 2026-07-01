
# 🚗 Vehicle Insurance MLOps Pipeline

> End-to-End MLOps Pipeline for Vehicle Insurance Prediction using **FastAPI, MongoDB, Docker, AWS, GitHub Actions, and Amazon ECR**.

## 🚀 Features

- End-to-End ML Pipeline
- Data Ingestion from MongoDB Atlas
- Data Validation & Transformation
- Model Training & Evaluation
- AWS S3 Model Registry
- FastAPI Web Application
- Dockerized Deployment
- CI/CD using GitHub Actions
- Self-Hosted GitHub Runner
- Deployment on AWS EC2

---

# 🏗️ Architecture

```text
Dataset
   │
   ▼
MongoDB Atlas
   │
   ▼
Data Ingestion
   │
   ▼
Data Validation
   │
   ▼
Data Transformation
   │
   ▼
Model Training
   │
   ▼
Model Evaluation
   │
   ▼
AWS S3 Model Registry
   │
   ▼
Docker Image
   │
   ▼
Amazon ECR
   │
   ▼
GitHub Actions
   │
   ▼
AWS EC2
   │
   ▼
FastAPI Application
```

# 📂 Project Setup

## 1. Create Project Template

```bash
python template.py
```

## 2. Configure Local Package

Update:

- `setup.py`
- `pyproject.toml`

## 3. Create Virtual Environment

```bash
conda create -n vehicle python=3.10 -y
conda activate vehicle
pip install -r requirements.txt
pip list
```

# 🍃 MongoDB Atlas Setup

1. Create MongoDB Atlas account.
2. Create a new project.
3. Create an M0 Cluster.
4. Create a database user.
5. Add Network Access:

```text
0.0.0.0/0
```

6. Copy the Python connection string.

Set environment variable:

### Linux/macOS

```bash
export MONGODB_URL="mongodb+srv://<username>:<password>@..."
```

### Windows PowerShell

```powershell
$env:MONGODB_URL="mongodb+srv://<username>:<password>@..."
```

# ⚙️ ML Pipeline

- Data Ingestion
- Data Validation
- Data Transformation
- Model Trainer
- Model Evaluation
- Model Pusher
- Prediction Pipeline

# ☁️ AWS Setup

## IAM

Create an IAM user and generate:

- AWS_ACCESS_KEY_ID
- AWS_SECRET_ACCESS_KEY

## S3

Bucket:

```text
my-model-mlopsproj
```

Region:

```text
us-east-1
```

# 🐳 Docker

Build

```bash
docker build -t vehicleproj .
```

Run

```bash
docker run -p 5000:5000 vehicleproj
```

# 🚀 CI/CD

## Amazon ECR

Create repository:

```text
vehicleproj
```

Push Docker image to ECR.

## EC2

Launch Ubuntu instance.

Install Docker:

```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker ubuntu
newgrp docker
```

## Self Hosted Runner

GitHub → Settings → Actions → Runners → New Self Hosted Runner

Run generated commands on EC2.

# 🔐 GitHub Secrets

- AWS_ACCESS_KEY_ID
- AWS_SECRET_ACCESS_KEY
- AWS_DEFAULT_REGION
- ECR_REPO

# 🌐 Security Group

Open:

| Port | Purpose |
|------|---------|
|22|SSH|
|80|HTTP|
|443|HTTPS|
|5000|FastAPI|

# ▶️ Run Application

```bash
uvicorn app:app --host 0.0.0.0 --port 5000
```

Visit:

```text
http://<EC2_PUBLIC_IP>:5000
```

Training endpoint:

```text
http://<EC2_PUBLIC_IP>:5000/training
```

# 📸 Screenshots

Add screenshots for:

- Home Page
- GitHub Actions
- AWS ECR
- EC2
- MongoDB
- S3
- Docker

# 📄 License

MIT License.

---

⭐ **If you found this project useful, please give it a star!**
