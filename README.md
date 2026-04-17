# ONDC_IndiaAI_Innovation_challenge_2026_OPEN

ZOMAKARB AI SOLUTIONS: ONDC MSE AGENT MAPPING TOOL PROJECT OVERVIEW
ZOMAKARB AI Solutions is an AI-powered onboarding and matchmaking platform. 
It is designed to seamlessly connect Micro and Small Enterprises (MSEs) with the most suitable partner networks (SNPs) on the Open Network for Digital Commerce (ONDC).

THE PROBLEM
The current process of integrating MSEs onto the ONDC platform under the TEAM initiative is highly inefficient.It relies on manual data entry, inconsistent product cataloguing, and labour-intensive NSIC verifications.These inefficiencies cause severe delays and application rejections.Complex forms, language barriers, and inefficient SNP mapping cause massive friction for MSEs joining ONDC.

THE SOLUTION
ZOMAKARB provides a zero-learning-curve, multilingual voice agent.Voice-First Input: MSEs just talk to the app, and it auto-fills forms using Bhashini ASR/TTS.Automated Standardization: It moves from static web forms to a dynamic, conversational UI that automatically standardizes unstructured speech into an ONDC-compliant taxonomy.

TECHNOLOGY STACK
Frontend: React.
Backend: FastAPI.Voice & Translation: Bhashini.Edge AI & Reasoning: Ollama for local AI reasoning, using models like mxbai-embed-large:latest, llava:vision language, and qwen2.5-instruct.Database & Vector Store: ChromaDB for embeddings and Retrieval-Augmented Generation (RAG).

CORE FEATURES
Multilingual UI: A language drop down translates the UI of the whole platform.
Voice Assistance: Bhashini Text to Speech gives support by listening to the user for every question and giving hints.
ONDC AskBot: A smart chatbot powered by the Ollama model that has the context of the real time dashboard details to help in every step of form filling.
Smart Error Handling: Detects mismatches, such as a name mismatch between the ID Proof and introduction, prompting the user to select the correct name.
Partner Mapping: The Ollama model maps the best possible logistics and tech partners based on a pre-defined point system. 
For example, an exact ONDC category code match is +50 points.

RESPONSIBLE AI & DATA SECURITY
Privacy: Processing reasoning locally via Ollama ensures sensitive business data isn't exposed to public APIs.
Inclusivity: Bhashini integration ensures non-English speaking, rural, or low-literacy MSEs have equal access to digital commerce.
Compliance: Adheres to the DPDP Act and Guidelines for Indian Government Websites (GIGW) by minimizing data retention and securing the FastAPI backend.

PRODUCT ROADMAP
Phase 1: Deploy the React/FastAPI stack with Bhashini integration and SQLite/JSON databases for initial ONDC pilots.
Phase 2: Scale up to ChromaDB for nationwide RAG-based matching and shift to PostgreSQL.
Phase 3: System Integration with National Small Industries Corporation (NSIC) APIs for automated claim verification.

TEAM & LINKS
Co-Founders: Avani Sehgal, Agam Dayal, Aryaman Sharma, Rajani Kant Jha.
Live Demo: https://zomakarb.vercel.app/.
Contact: zomakarb@gmail.com.
