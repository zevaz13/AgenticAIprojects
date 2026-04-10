### 🧠 Agentic AI Resume Improvement System

This project implements a multi-agent AI architecture for automatically improving and rewriting resumes for candidates targeting roles in Data Science and AI Engineering.

It uses a hierarchical system of agents: an Advisor Manager that synthesizes expert feedback from multiple AI tools, and a Writer Agent that produces a final polished resume.

---

## 🏗️ System Architecture

The system is composed of two main agents:

1. Advisor Manager (Coordinator Agent)
Acts as the decision-making and synthesis layer
Orchestrates multiple advisory tools (specialized agents)
Combines and refines suggestions into a final improvement strategy
Hands off final structured guidance to the Writer Agent
2. Writer Agent (Generation Agent)
Responsible for producing the final optimized resume
Strictly follows instructions from the Advisor Manager
Does NOT generate new ideas or suggestions
Outputs a clean, one-page resume ready for PDF export

---

## 🔧 Tool-Based Advisory System

The Advisor Manager uses three specialized AI tools:

| Tool Name     | Model            | Role                                                         |
| ------------- | ---------------- | ------------------------------------------------------------ |
| `D_adv_Agent` | DeepSeek         | Data-focused resume critique and structure optimization      |
| `G_adv_Agent` | Gemini Flash 2.0 | Language clarity, phrasing, and engagement improvements      |
| `O_adv_Agent` | GPT-4o-mini      | ATS optimization, keyword enhancement, and formatting advice |

Each tool provides an independent perspective on improving the resume.
---

## 🔄 Workflow Pipeline

- CV + Current Resume  
  ↓  
- Advisor Manager  
  ↓  
- Agents  
  - D_adv_Agent (DeepSeek)  
  - G_adv_Agent (Gemini Flash)  
  - O_adv_Agent (GPT-4o-mini)  
  ↓  
- Combine + Rank Suggestions  
  ↓  
- Final Structured Improvement Plan  
  ↓  
- Writer Agent  
  ↓  
- Final Polished Resume (1-page)

---
## 🧑‍💼 Advisor Manager Instructions

The Advisor Manager is responsible for:

1. Generating suggestions
  - Must call all three advisory tools
  - Each tool provides a unique set of resume improvement suggestions
  - Maximum: 2 calls per tool if needed
2. Evaluating and combining
  - Compare outputs from all tools
  - Select the most effective suggestions
  - Merge them into a single coherent improvement strategy
3. Output format
  - Produce one detailed, structured set of resume improvement suggestions
  - Must be optimized for Data Science / AI Engineer roles
  - Must NOT use the word "leverage"
4. Handoff
-  Pass final suggestions to the Writer Agent

---

## ✍️ Writer Agent Instructions


Receives:
  - Original CV
  - Current resume
  - Final suggestions from Advisor Manager
Responsibilities:
  - Rewrite the resume using only provided suggestions
  - Do NOT invent new content
  - Do NOT modify beyond instructions received
Ensure:
  - Professional tone
  - ATS-friendly structure
  - Concise formatting
  - Maximum one-page output
Output rule:

  - Only return the final resume text (no explanations or metadata)
---
## 🧠 Key Design Principles

🔁 Separation of reasoning and generation
🧩 Multi-model ensemble for better suggestions
🎯 Strict instruction hierarchy
📄 One-page ATS-optimized resume output
🚫 No hallucinated experience or added content

---
## 🚀 Technologies Used

OpenAI Agents SDK  
GPT-4o-mini  
DeepSeek (D_adv_Agent)  
Gemini Flash 2.0 (G_adv_Agent)  
Multi-agent orchestration with tool-based handoffs  

---

##📌 Important Constraints

❌ No use of the word “leverage”
❌ Writer Agent must not modify or infer new content
❌ Advisor Manager must rely only on tool outputs
✅ Final output must be clean, structured, and recruiter-ready
