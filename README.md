# 🌐 **SmartCommunity AI – Multi-Agent Concierge System**

### Kaggle Google Gen AI Capstone Project

**Track:** Concierge Agents
**Model:** Gemini 1.5 Flash
**Framework:** Google Agent Development Kit (ADK – Python)

---

## 📌 **Overview**

SmartCommunity AI is a **multi-agent concierge system** designed for modern residential communities—apartment complexes, gated societies, PG/hostels, and senior-living facilities.

It automates daily coordination tasks such as:

* Errands (grocery, medicine pickup, parcel coordination)
* Maintenance (repairs, electrical/plumbing issues)
* Information Lookup (shop timings, emergency numbers, local details)
* Simple decision-making (best vendor choice, cost estimates)

Built entirely with **Gemini 1.5 Flash + Google ADK**, this project demonstrates multi-agent workflows, tool use, memory, evaluation, and observability—meeting all requirements of the Kaggle Gen AI Capstone.

---

# 🎯 **Problem Statement**

Daily tasks in residential communities are repetitive, confusing, and poorly coordinated.
Residents struggle with:

* Tracking grocery/med pickup options
* Comparing vendor prices
* Handling maintenance requests
* Searching for reliable information
* Coordinating with guards, staff, or neighbors

Elderly individuals, students, and busy professionals lose time due to manual processes.

---

# 💡 **Solution: SmartCommunity AI**

A **multi-agent automated concierge** that handles community life seamlessly:

### ✔ Orchestrator Agent

Routes user messages to the correct specialized agent using Gemini classification.

### ✔ Errand Agent

* Compares grocery/medicine vendors
* Finds cheapest option using the Vendor Pricing Tool
* Summarizes errands and next steps

### ✔ Maintenance Agent

* Helps diagnose issues (e.g., “Leaking tap”)
* Suggests quick fixes
* Estimates cost & logs a ticket

### ✔ InfoSearch Agent

Uses Google Search tool for:

* Shop hours
* Local news
* Contact information
* Weather, price checks, etc.

### ✔ Memory

Stores user preferences (e.g., store choice, home location, urgency).

### ✔ Observability

Logs, traces, and tool usage information included.

---

# 🧠 **Why Agents?**

A single LLM isn't enough for structured, multi-step operations.

Agents enable:

* **Tool calls** (search, pricing API)
* **Long-running operations**
* **Parallel & sequential workflows**
* **Context compaction**
* **Session memory**
* **Orchestration at scale**

This project uses **three key agent features (required by capstone):**
✔ Multi-agent system (4 agents)
✔ Tools (Google Search, Custom Pricing Tool)
✔ Memory (InMemorySessionService)
✔ Observability (structured logs & traces)

---

# 🏗 **Architecture Diagram**

```
                     ┌────────────────────────────┐
                     │   User Message Input        │
                     └──────────────┬─────────────┘
                                    │
                                    ▼
                        ┌──────────────────────┐
                        │  Orchestrator Agent  │
                        └───────┬─────┬────────┘
                                │     │
                     ┌──────────┘     └──────────┐
                     ▼                            ▼
        ┌─────────────────────┐       ┌─────────────────────┐
        │     Errand Agent    │       │  Maintenance Agent  │
        └─────────┬───────────┘       └───────────┬────────┘
                  │                              │
        ┌─────────▼───────────┐        ┌─────────▼───────────┐
        │ Vendor Pricing Tool  │        │ Ticket/Repair Logic  │
        └──────────────────────┘        └──────────────────────┘

                     ┌────────────────────────────────────────┐
                     │         InfoSearch Agent               │
                     └─────────┬──────────────────────────────┘
                               ▼
                       Google Search Tool
```

---

# 🛠 **Tech Stack**

| Component             | Choice                                    |
| --------------------- | ----------------------------------------- |
| LLM                   | **Gemini 1.5 Flash**                      |
| Multiplicity          | Multi-agent (Orchestrator + 3 sub-agents) |
| Memory                | InMemorySessionService                    |
| Tools                 | Custom Vendor Pricing Tool, Google Search |
| Observability         | Logs, traces                              |
| Evaluation            | Built-in ADK eval methods                 |
| Notebook              | Kaggle                                    |
| Deployment (optional) | Cloud Run                                 |

---

# 📂 **Repository Contents**

```
📦 SmartCommunity-AI
 ┣ 📄 README.md
 ┣ 📓 SmartCommunity_Kaggle_Notebook_ADK.ipynb
 ┣ 📁 images/ (slide deck assets + thumbnails)
 ┣ 📄 architecture.png
 ┗ 📄 requirements.txt
```

---

# 📘 **Kaggle Notebook**

The full notebook containing all agents, tools, memory, evaluation, and step-by-step explanations:

👉 **SmartCommunity_Kaggle_Notebook_ADK.ipynb**
*(included in this repo)*

---

# ⚙️ **Setup & Installation**

### 1️⃣ Clone repo

```
git clone https://github.com/<your-username>/SmartCommunity-AI.git
cd SmartCommunity-AI
```

### 2️⃣ Install dependencies

```
pip install -r requirements.txt
```

### 3️⃣ Set Gemini API Key

Create an environment variable:

```
export GOOGLE_API_KEY="YOUR_KEY"
```

For Kaggle:
**Settings → Secrets → Add New Secret → GOOGLE_API_KEY**

---

# 🚀 **Running the Agents**

Run in local Python:

```python
from agents import orchestrator_agent

response = orchestrator_agent.run("I need to pick up groceries")
print(response)
```

Or open the provided **Kaggle notebook** and run all cells.

---

# 🎥 **Demo Video (Bonus Section)**

Upload your YouTube demo video here:

🔗 **YouTube Link:** *coming soon*

Script & slide prompts included in the `/video/` folder.

---

# 🧪 **Evaluation**

The notebook includes:

* Agent evaluation examples
* Observability logs
* Traces of all tool calls
* Consistency checks

These demonstrate ADK capabilities required by the capstone submission.

---

# ☁️ **Deployment (Optional)**

The repository contains instructions to deploy on:

* Google Cloud Run
* Vertex AI Agent Engine

Using the same ADK code with environment credentials.

---

# 🏁 **Conclusion**

SmartCommunity AI demonstrates how multi-agent systems powered by Gemini can automate everyday community tasks, creating a reliable concierge for residential living.
