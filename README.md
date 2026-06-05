# 🚗 Car Contract AI Assistant

An AI-powered backend system that extracts, analyzes, and structures car contract information using LLMs, document parsing, and REST APIs.

---

## 📌 Overview

Car Contract Assistant is a modular backend application built with **FastAPI** that:

* 📄 Parses car contract documents
* 🔍 Extracts structured data (VIN, pricing, contract terms)
* 🤖 Uses LLM to refine and structure outputs
* 🗄 Stores processed results in a database
* 🐳 Supports Docker-based deployment

---

## 🏗 Project Architecture

The project follows a **layered and modular architecture** to ensure scalability and clean separation of concerns.

```
car_contract_assistant/
│
├── backend/
│   ├── app/
│   │   ├── api/                # API endpoints (FastAPI routes)
│   │   ├── services/           # Business logic layer
│   │   ├── core/               # Config & database setup
│   │   ├── models/             # Database models & schemas
│   │   ├── utils/              # Helper utilities
│   │   ├── __init__.py
│   │   └── main.py             # Application entry point
│   │
│   ├── Dockerfile
│   ├── docker-compose.db.yml
│   └── requirement.txt
│
├── data/                       # Sample or processed data
├── frontend/                   # Frontend application (if applicable)
├── tests/                      # Unit & integration tests
│
├── .env                        # Environment variables
├── init_database.py            # Database initialization script
├── docker-compose.yml          # Full stack container setup
├── Screenshot
├── LICENSE
└── README.md
```

---

## 🧠 Architecture Layers

### 1️⃣ API Layer (`app/api/`)

* Handles HTTP requests
* Performs validation
* Returns structured responses

### 2️⃣ Service Layer (`app/services/`)

* Contains business logic
* Contract parsing
* VIN extraction
* LLM interaction
* Data processing

### 3️⃣ Core Layer (`app/core/`)

* Configuration management
* Environment variables
* Database connection setup

### 4️⃣ Models Layer (`app/models/`)

* ORM models
* Pydantic schemas
* Data validation

### 5️⃣ Utilities (`app/utils/`)

* Shared helper functions
* Reusable logic

---

## 🔄 Request Flow

```
Client Request
      ↓
API Layer
      ↓
Service Layer
      ↓
LLM / Parser / Database
      ↓
Structured Response
      ↓
Client
```

---

## 🚀 Features

* REST API using FastAPI
* Modular service-based architecture
* LLM-powered contract analysis
* VIN extraction service
* Structured JSON output
* Dockerized deployment
* Environment-based configuration
* Database integration

---

## 🛠 Tech Stack

* **Backend:** FastAPI
* **Language:** Python 3.10+
* **Database:** PostgreSQL / SQLite (configurable)
* **ORM:** SQLAlchemy
* **Validation:** Pydantic
* **Containerization:** Docker & Docker Compose
* **LLM Integration:** OpenAI API / Compatible LLM

---

## ⚙️ Local Installation

### 1️⃣ Clone Repository

```bash
git clone https://github.com/your-username/car_contract_assistant.git
cd car_contract_assistant
```

---

### 2️⃣ Create Virtual Environment

```bash
python -m venv .venv
```

Activate:

**Mac/Linux**

```bash
source .venv/bin/activate
```

**Windows**

```bash
.venv\Scripts\activate
```

---

### 3️⃣ Install Dependencies

```bash
pip install -r backend/requirement.txt
```

---

### 4️⃣ Configure Environment Variables

Create a `.env` file in the root directory:

```
DATABASE_URL= postgresql+psycopg2://car_user:password@localhost:5433/car_contracts_db
OPENAI_API_KEY=your_openai_api_key
ENVIRONMENT=development
```

---

### 5️⃣ Initialize Database

```bash
python init_database.py
```

---

### 6️⃣ Run Application

```bash
uvicorn backend.app.main:app --reload
```

Open API documentation:

```
http://127.0.0.1:8000/docs
```

---

## 🐳 Docker Deployment

Run full stack with Docker:

```bash
docker-compose up --build
```

This will:

* Build backend container
* Start database container
* Connect services automatically




---

## 🌐 Deployment

You can deploy using:

* Render
* Railway
* AWS EC2
* Azure
* Docker-based VPS

My deployment link:

```
https://car-contract-ai-assistant-efik.onrender.com
```

---



## 🔐 Environment Variables

| Variable       | Description                |
| -------------- | -------------------------- |
| DATABASE_URL   | Database connection string |
| OPENAI_API_KEY | API key for LLM            |
| ENVIRONMENT    | development / production   |


---

## 📜 License

This project is licensed under the MIT License.
