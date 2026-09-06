# ⚡ EnclaveDoc AI // The Autonomous Compliance & Forensic Engine
> **No cap, enterprise paperwork is broken.**  
> We didn't just build another boring PDF validator. EnclaveDoc AI is an air-gapped forensic audit suite that cross-examines unstructured forms against regulatory standards in an isolated zero-egress sandbox. 

[![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)](https://streamlit.io/)
[![FAISS](https://img.shields.io/badge/VectorDB-FAISS-04A658?style=for-the-badge)](https://github.com/facebookresearch/faiss)
[![Local LLM](https://img.shields.io/badge/Inference-Local_GGUF_Air--Gapped-black?style=for-the-badge)](https://github.com/ggerganov/llama.cpp)
[![License: MIT](https://img.shields.io/badge/License-MIT-purple?style=for-the-badge)](https://opensource.org/licenses/MIT)

---

## 🔥 Beyond "Document Verification"

Most tools just check if a text box is empty and call it a day. **EnclaveDoc AI runs full legal & policy forensic audits.** 

Whether it's KYC dossiers, banking agreements, or medical waivers, the system cross-checks what’s inside your document against an indexed regulatory rulebook. If an applicant missed a clause, forged a date, or skipped a mandatory statutory declaration, EnclaveDoc calls it out instantly with exact clause citations and visual forensic markers.

And the best part? **Zero data leaves your machine.** Run it 100% offline in a hardware enclave using quantized GGUF models, or flip the switch to ultra-fast cloud inference when speed is priority.

---

## 🛰️ The Dual-Core Forensic Pipeline

```text
 ┌──────────────────────────────────────────────────────────────┐
 │                GROUND-TRUTH POLICY VAULT                     │
 │     Statutory PDFs ──► Chunking ──► FAISS Vector Matrix      │
 └──────────────────────────────┬───────────────────────────────┘
                                │
                                ▼
 ┌──────────────────────────────────────────────────────────────┐
 │                  INCOMING FORM INGESTION                     │
 │     Unstructured Document ──► Structural Parsing & OCR       │
 └──────────────────────────────┬───────────────────────────────┘
                                │
                                ▼
 ┌──────────────────────────────────────────────────────────────┐
 │                DUAL-INFERENCE SANDBOX                        │
 │                                                              │
 │   [AIR-GAPPED ENCLAVE MODE]          [TURBO CLOUD MODE]      │
 │   llama-cpp-python                   Gemini 1.5 Flash/Pro    │
 │   Local Quantized GGUF               High-throughput API     │
 │   (100% Offline / Zero Leaks)                                │
 └──────────────────────────────┬───────────────────────────────┘
                                │
                                ▼
 ┌──────────────────────────────────────────────────────────────┐
 │     AUDIT OUTPUT: Discrepancy Bounding Boxes + Scorecard     │
 └──────────────────────────────────────────────────────────────┘
```
🧬 Core Intelligence Specs
| Feature | What It Actually Does | Why It Hits Different |
| :--- | :--- | :--- |
| **🔒 Air-Gapped Sandbox** | Runs on quantized 4-bit local GGUF models via `llama-cpp-python` | Zero internet connection required. Strict KYC and PII data never touch external servers. |
| **⚡ Turbo Cloud Engine** | Instant API orchestration via Google Gemini | Processes huge batch queues in seconds when privacy compliance permits. |
| **🎯 Vector Clause Matching** | High-density semantic vector search powered by FAISS & Sentence-Transformers | Matches complex legalese against precise clauses—no lazy keyword matching. |
| **🔎 Forensic Discrepancy Finder** | Finds omitted fields, expired validity dates, and conflicting statements | Flags exactly what is wrong, why it violates policy, and where it happened. |
| **📊 One-Click Audit Dossier** | Generates a timestamped JSON/PDF compliance ledger on the fly | Ready-to-ship proof for legal, risk management, and compliance reviews.|

🛠️ Tech Arsenal
```text
Interface Layer:      Streamlit (Glassmorphic dark dashboard)
Vector Retrieval:     FAISS (Facebook AI Similarity Search)
Semantic Embeddings:  sentence-transformers/all-MiniLM-L6-v2
Orchestration:        LangChain Core Pipeline
Local Enclave:        llama-cpp-python (Mistral-7B / TinyLLaMA 4-bit Quantized GGUF)
Cloud Inference:      Google Gemini Pro / Flash API
Document Extraction:  PyPDF / PyMuPDF (fitz)
```
🕹️ Quickstart & Local Deployment
1. Clone & Set Up Virtual Environment
 ```text
git clone [https://github.com/Khushirajora/EnclaveDoc-AI.git](https://github.com/Khushirajora/EnclaveDoc-AI.git)
cd EnclaveDoc-AI

python -m venv venv
.\venv\Scripts\Activate.ps1
```
2. Install Dependencies
 ```text

pip install -r requirements.txt
```

3. Configure Hardware & Secrets
Create a .env file in the root folder:
```text
# Optional: Only needed for Turbo Cloud Mode
GEMINI_API_KEY=your_gemini_api_key_here

# Local Model Weights (Air-Gapped Enclave Mode)
LOCAL_MODEL_PATH=./models/mistral-7b-instruct-v0.2.Q4_K_M.gguf
```
4. Boot Up the Dashboard
   ```text
   streamlit run app.py
   ```

📡 Live Forensic Audit Payload
What the engine outputs after tearing down a submission:
```text
{
  "document_id": "KYC_APPLICANT_9042.pdf",
  "audit_verdict": "FLAGGED",
  "risk_index": "HIGH",
  "integrity_score": 78.5,
  "execution_mode": "Air-Gapped Enclave (Mistral-7B-GGUF)",
  "compliance_violations": [
    {
      "clause_violated": "Section 4.1: Statutory Identity & Proof of Residency",
      "flagged_issue": "Utility statement timestamp exceeds 90-day threshold",
      "severity": "CRITICAL",
      "suggested_action": "Request updated billing receipt from past 30 days"
    },
    {
      "clause_violated": "Section 9.2: Authorized Signatures",
      "flagged_issue": "Digital signature block unverified / missing cryptographic hash",
      "severity": "MEDIUM",
      "suggested_action": "Require wet-ink scan or e-sign certificate validation"
    }
  ]
}
```

