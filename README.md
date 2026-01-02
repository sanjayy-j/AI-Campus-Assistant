# 🤖 AI Campus Assistant (Agentic RAG System)

A multi-modal AI agent designed to assist university students by answering campus queries and logging student grievances. Built using **Google Gemini Flash**, **LangChain**, and **ChromaDB**.

## 📌 Project Overview
This project was built to solve the disconnect between static campus rules (PDFs) and actionable student needs. It evolves from a simple chatbot into an **Autonomous Agent** capable of decision-making.

### 🚀 Features (The 3-Level Architecture)

**Level 1: Foundation (Conversational AI)**
* Integrated **Gemini Flash** for natural language understanding.
* Established a secure, latency-optimized inference pipeline.
* Implemented "System Persona" steering to ensure professional, domain-specific responses.

**Level 2: RAG (Retrieval-Augmented Generation)**
* **Ingestion:** Parsed unstructured domain data (`vit_handbook.txt`).
* **Vector Database:** Utilized **ChromaDB** with local embeddings (`HuggingFace all-MiniLM`) to eliminate API rate limits.
* **Grounding:** Implemented semantic search to retrieve accurate context and prevent hallucinations.

**Level 3: Agentic Workflow (Autonomous Actions)**
* **Tool Use:** Enabled **Function Calling**, giving the AI the ability to "do" things, not just "read" things.
* **Decision Engine:** The Agent intelligently routes queries:
    * *Informational queries* ("When is the exam?") → Trigger **Retrieval Tool**.
    * *Actionable complaints* ("Wifi is broken") → Trigger **Complaint Logging Tool**.
    * *General Chit-chat* ("Hi") → **Direct Response** (No tool usage).

---

## 🛠️ Tech Stack
* **LLM:** Google Gemini 1.5 Flash
* **Orchestration:** LangChain / Google GenAI SDK
* **Vector Store:** ChromaDB (Persistent Local Storage)
* **Embeddings:** HuggingFace (`all-MiniLM-L6-v2`)
* **Environment:** Google Colab

---

## 📂 Repository Structure

```text
├── notebooks/
│   └── ai_campus_assistant.ipynb  
├── data/
│   └── vit_handbook.txt           
├── logs/
│   └── complaints.txt            
├── README.md                     
└── LICENSE
```
## ⚡ How to Run
1.  **Open in Colab:** Open the `notebooks/ai_campus_assistant.ipynb` file in Google Colab.
2.  **Set Secrets:** Add your **Google AI Studio API Key** in the Colab Secrets manager (Name: `GOOGLE_API_KEY`).
3.  **Initialize:** Run all cells to download the embedding model, ingest the handbook, and initialize the Agent.
4.  **Interact:** Chat with the bot in the interactive input box at the bottom!

## 📜 Future Improvements
* **Frontend:** Add a web UI using Streamlit or Gradio.
* **Enhanced Ingestion:** Expand the Knowledge Base to include automatic PDF parsing.
* **Long-Term Memory:** Implement vector-based memory to remember student details across sessions.
