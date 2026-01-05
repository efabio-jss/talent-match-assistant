# 🧠 Talent Match Assistant

**Talent Match Assistant** is a Streamlit-based recruitment intelligence tool designed to help recruiters and hiring managers quickly and objectively assess how well candidate CVs match a given job description.

The application focuses on **explainability, efficiency, and decision support**, enabling better shortlisting, structured interviews, and reduced manual effort during early-stage screening.

---

## 🚀 Key Features

### 🔍 CV vs Job Description Analysis
- Upload one or multiple CVs (PDF or DOCX)
- Paste job descriptions directly into the app
- Automatic, structured comparison between CV and role requirements

### 📊 Explainable Scoring
- Overall match score (0–100)
- Recommendation: **Strong Yes / Yes / Maybe / No**
- Explainable subscores:
  - Skills
  - Experience
  - Tools
  - Domain fit
- Transparent reasoning and evidence extracted from the CV

### 🧾 Shortlist & Ranking
- Automatic **shortlist** based on a configurable score threshold
- Ranking of all candidates by match score
- Side-by-side comparison of up to 5 candidates

### 🎯 Interview Guide (Gap-Focused)
- Interview questions automatically generated from identified gaps
- Separation between:
  - Critical checks
  - Nice-to-have validations
- Designed to improve interview quality and objectivity

### 📝 Recruiter Notes
- Add recruiter notes per candidate
- Notes are stored in session state
- Notes are included in all exports and copy actions

### 📤 Export & Actions
- Copy full analysis report to clipboard (1-click)
- Export candidate reports to:
  - PDF
  - DOCX
- Reports include scoring, analysis, interview guide, and recruiter notes

### 🧠 History & Session Management
- History of all analyses in the session
- Reload previous candidates
- Two reset modes:
  - **Clear inputs** (keeps history)
  - **Reset session (delete history + uploaded CVs)**

---

## 🏗️ Architecture Overview

```text
Streamlit UI
   |
   |-- Job Description (text)
   |-- CV Uploads (PDF / DOCX)
   |
AI Evaluation Engine (OpenAI API)
   |
   |-- Structured JSON scoring
   |-- Explainable reasoning
   |
Post-processing
   |
   |-- Shortlist logic
   |-- Ranking & comparison
   |-- Interview guide generation
   |
Exports
   |-- Clipboard
   |-- PDF
   |-- DOCX


🧩 Technology Stack

Python 3.10+

Streamlit – UI & interaction layer

OpenAI API – structured AI evaluation

python-dotenv – environment variable management

reportlab – PDF generation

python-docx – DOCX export

Custom CV extraction utilities (PDF / DOCX)


⚙️ Local Setup
1️⃣ Clone repository
git clone https://github.com/efabio-jss/talent-match-assistant.git
cd talent-match-assistant

2️⃣ Create virtual environment
python -m venv .venv
  Activate:
    Windows
      .venv\Scripts\Activate.ps1
    macOS / Linux
      source .venv/bin/activate

3️⃣ Install dependencies
pip install -r requirements.txt

4️⃣ Environment variables
Create a .env file:
  OPENAI_API_KEY=your_api_key_here
  OPENAI_MODEL=gpt-4o-mini

5️⃣ Run the app
streamlit run app.py


🧪 Intended Use Cases
Recruiters screening high volumes of CVs
Hiring managers validating shortlists
Structured interview preparation
Internal recruitment analytics demos
proof-of-concept for AI-assisted hiring tools


🛣️ Scalable to:
Integration with ATS platforms 
Interview scheduling (Microsoft Teams / Outlook)
Persistent storage (database-backed history)
Role-specific scoring templates
Bias & compliance guardrails
Analytics dashboard (pipeline, conversion rates, time-to-hire)
  
⚠️ Disclaimer
This tool is designed to assist recruiters, not replace human decision-making.
All evaluations are based solely on the information provided in CVs and job descriptions.
