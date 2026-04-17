# 🚀 ONDC MSE Agent 👨🏻‍🦱

### AI-Powered Voice-First Multilingual Onboarding for Indian Micro & Small Enterprises (MSEs)

[![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)](https://fastapi.tiangolo.com/)
[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)](https://www.mongodb.com/)
[![Ollama](https://img.shields.io/badge/Ollama-AI-white?style=for-the-badge&logo=ollama)](https://ollama.com/)

---

## 🌟 Overview

The **ONDC MSE Agent** is a state-of-the-art onboarding system designed to bridge the digital divide for Micro and Small Enterprises (MSEs) in India. By leveraging cutting-edge AI, it allows merchants to join the [Open Network for Digital Commerce (ONDC)](https://ondc.org/) using their **native language** through a voice-first interface.

### The Problem
Digitizing a product catalog and finding the right Seller Network Participant (SNP) can be daunting for small merchants due to:
- **Language Barriers**: Complexity of complex digital forms in non-native languages.
- **Technical Friction**: Manual data entry for product catalogs.
- **Discovery Issues**: Identifying which SNP best suits their specific product category and location.

### The Solution
A multi-modal AI agent that:
1. **Listens** to the merchant's description in their native language (11+ Indic languages).
2. **Sees** and analyzes product images to extract features automatically.
3. **Generates** ONDC-compliant catalog schemas.
4. **Matches** the merchant with the most compatible SNPs using semantic search.

---

## ✨ Key Features

### 🎤 Multilingual Voice Onboarding
- Powered by **Bhashini API**.
- Supports 11+ Indian languages including Hindi, Tamil, Telugu, Bengali, Marathi, and more.
- Real-time ASR (Automatic Speech Recognition) and NMT (Neural Machine Translation).

### 📷 AI Product Cataloging
- **Vision Model (LLaVA)**: Analyzes product images to detect categories, ingredients, and attributes.
- **Intelligent Extraction**: Extracts product names and details from spoken introductions and ID proofs.

### 🔍 Intelligent SNP Matching
- **Semantic Re-ranking**: Uses **Qwen 2.5** and vector embeddings to match MSEs with SNPs based on category, city, and technical capabilities.
- **Multi-Pass Filtering**: Combines deterministic logic with AI-driven reasoning to provide the best partner pools (Seller NPs, Logistics, and TSPs).

### 📝 ONDC-Compliant Generation
- Automatically generates structured JSON catalogs that adhere to ONDC protocols.
- Minimizes manual errors and speeds up the "Go-to-Market" time for small businesses.

---

## 🏗️ Architecture

```mermaid
graph TD
    A[MSE Merchant] -->|Voice/Image| B(React Frontend)
    B -->|Audio/Base64| C[FastAPI Backend]
    
    subgraph "AI Services Layer"
        C -->|ASR/NMT| D[Bhashini API]
        C -->|Vision/Catalog| E[Ollama - LLaVA]
        C -->|LLM/Logic| F[Ollama - Qwen 2.5]
    end
    
    subgraph "Data Layer"
        C -->|SNP Registry| G[(PostgreSQL)]
        C -->|Generated Catalogs| H[(MongoDB)]
    end
    
    C -->|Response| B
    B -->|UI Feedback| A
```

---

## 🛠️ Tech Stack

- **Frontend**: React 18, Vite, CSS Modules, Glassmorphic UI.
- **Backend**: FastAPI (Python 3.10+), SQLAlchemy (Async), Pydantic v2.
- **Databases**: PostgreSQL (Relational data), MongoDB (Unstructured catalogs).
- **AI Infrastructure**:
  - **Ollama**: Local LLM hosting.
  - **Bhashini**: Government of India's AI for Indic languages.
- **DevOps**: Ngrok (for local tunneling), Docker (optional).

---

## 🚀 Installation & Setup

### Prerequisites
- Python 3.10+
- Node.js 18+
- PostgreSQL & MongoDB
- [Ollama](https://ollama.com/) (for local AI functionality)

### 1. Initialize AI Models (Ollama)
Pull the required models to your local machine:
```bash
ollama pull qwen2.5:7b-instruct
ollama pull llava:7b
ollama pull mxbai-embed-large
```

### 2. Backend Setup
```bash
cd backend
python -m venv venv
source venv/bin/activate  # venv\Scripts\activate on Windows
pip install -r requirements.txt
cp .env.example .env  # Configure your keys here
```

### 3. Database Initialization
Seed the SNP (Seller Network Participant) registry:
```bash
python ../database/seed_snp_data.py
# For advanced ETL
python ../database/etl_snp_registry.py
```

### 4. Frontend Setup
```bash
cd frontend
npm install
npm run dev
```

---

## 🔧 Configuration (.env)

Edit `backend/.env` with your credentials:

```env
# Database
POSTGRES_URL=postgresql+asyncpg://user:pass@localhost:5432/ondc_mse
MONGODB_URL=mongodb://localhost:27017
MONGODB_DB=ondc_catalog

# Bhashini API
BHASHINI_API_KEY=your_key
BHASHINI_USER_ID=your_id
BHASHINI_ULCA_API_KEY=your_ulca_key

# Ollama
OLLAMA_BASE_URL=http://localhost:11434
```

---

## 📚 API Reference

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/api/process-voice` | POST | ASR + Translation for Indic languages |
| `/api/analyze-product` | POST | AI product analysis (Vision + Text) |
| `/api/match-snps-json` | POST | Integrated multi-pass partner matching |
| `/api/complete-onboarding` | POST | End-to-end workflow execution |
| `/api/extract-name` | POST | Extracts name from ID image or voice |
| `/health` | GET | Check system health |

---

## 🎨 UI Aesthetics

The application features a **"Modern Deep-Tech"** aesthetic:
- **Glassmorphism**: Frosted glass cards and overlays.
- **Interactive Feedback**: Real-time waveform visualization during voice recording.
- **Micro-animations**: Smooth transitions and AI "scanning" indicators.

---

## 📄 License

This project is licensed under the **MIT License**.

Built with ❤️ for the ONDC Ecosystem | 2026
