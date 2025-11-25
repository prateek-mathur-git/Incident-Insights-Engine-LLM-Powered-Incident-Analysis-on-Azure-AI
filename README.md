# Incident-Insights-Engine-LLM-Powered-Incident-Analysis-on-Azure-AI

This project demonstrates how Large Language Models (LLMs) can streamline IT Operations by analyzing incidents, extracting actionable insights, and accelerating MTTR.
Built entirely on Azure AI Services, the solution shows how enterprises can move from reactive firefighting to LLM-assisted intelligent operations.


---

🚀 Project Summary

Modern IT teams drown in alerts. Repeat noise, incomplete tickets, and inconsistent descriptions lead to:

Slow Root Cause Analysis (RCA)

Delays in identifying patterns across incidents

High MTTR and frustrated stakeholders

Lack of usable insights for SRE/Operations leadership


This project uses Azure AI + Generative AI to convert raw incident text into structured, high-quality intelligence.

You upload raw incidents → LLM processes each → Outputs structured JSON with fields like:

Probable cause

Category

Severity alignment

Recommended actions

Similar incident grouping

RCA hints


This is the building block of an AIOps insight engine.


---

🧠 What This Project Demonstrates

✔ How to build a real GenAI use-case without deep coding
✔ How Ops teams can adopt LLM-based incident intelligence
✔ How Azure AI Search + LLMs enrich operational data
✔ A starter template for AIOps / Observability / SRE automation portfolios
✔ A foundation you can extend into full RCA, response automation & correlation


---

🏗️ Architecture Overview

Input (Incidents) → Azure AI Indexing → LLM Analysis → Structured Output in JSON

Components used:

Azure AI Foundry

Azure AI Search (indexers, skillsets, cognitive enrichment)

Azure OpenAI Models (GPT-4o or Phi-4 depending on availability)

Python-based batch processing (Optional enhancement)

Azure Storage (data source)



---

📂 Project Structure

/incident-insights-engine
│
├── dataset/
│   └── incidents.json         # Sample dataset with raw incidents
│
├── notebooks/
│   └── batch_llm_process.ipynb   # Notebook to call Azure AI for enrichment
│
├── flow_diagram/
│   └── architecture.png        # Visual architecture overview
│
└── README.md                   # Project overview


---

📘 How It Works (Step-by-Step)

1️⃣ Prepare your dataset

Dataset must be in JSON or NDJSON, one incident per line.

Example:

{
  "id": "INC001",
  "description": "Database latency observed on shard-2",
  "service": "Database",
  "severity": "P2"
}


---

2️⃣ Create Azure AI Search Index

Create index

Define fields:
id, description, service, severity, enriched_data

Upload JSON/NDJSON file

Run indexer



---

3️⃣ Enrich using Azure AI Skillset

Attach a skillset with:

Custom Text Analytics

LLM Skill calling gpt-4o-mini or phi-4

Output JSON fields



---

4️⃣ Run Query

Ask:

> "What’s the probable cause?"
"Group similar incidents"
"Recommend RCA direction"


---

5️⃣ Export Results (for dashboards/RCA automation)


---

📊 Example Output (Structured)

{
  "id": "INC001",
  "probable_cause": "Database connection pool exhaustion",
  "category": "Performance",
  "severity_validated": "P2",
  "recommended_actions": [
    "Scale up database tier",
    "Increase max connection pool limit",
    "Check slow queries"
  ],
  "similar_incidents": ["INC004", "INC023"]
}


---

🧩 Use Cases This Can Power

🔸 Noise Reduction – auto-merge duplicates

🔸 RCA Assistant – LLM identifies dependencies and failure paths

🔸 SRE Dashboards – better context for leaders

🔸 On-call Copilot – recommended actions in real-time

🔸 AIOps Correlation Engine – extend into metric/log/trace correlation
