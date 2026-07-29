# HireLens AI

<div align="center">

# 🤖 HireLens AI

### AI-Powered Recruitment Screening & Candidate Evaluation System

An intelligent recruitment automation workflow built with **n8n**, **LLMs**, **Gmail**, and **Google Sheets** to automate CV screening, evaluate candidates against job descriptions, and streamline the hiring process.

![n8n](https://img.shields.io/badge/n8n-Automation-EA4B71?style=for-the-badge&logo=n8n&logoColor=white)
![OpenAI](https://img.shields.io/badge/LLM-AI-412991?style=for-the-badge&logo=openai&logoColor=white)
![Google Sheets](https://img.shields.io/badge/Google%20Sheets-34A853?style=for-the-badge&logo=googlesheets&logoColor=white)
![Gmail](https://img.shields.io/badge/Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

</div>

---

## 📌 Overview

**HireLens AI** is an end-to-end AI recruitment screening system that automatically receives job applications via email, extracts information from both the email body and attached CV, identifies the intended job position, retrieves the corresponding job description, evaluates the candidate using an intelligent scoring model, stores the results, and sends professional email responses.

The entire workflow is built in **n8n** and designed for production-ready recruitment automation.

---

## 🚀 Features

✅ Monitor incoming job application emails automatically

✅ Extract text from PDF CVs

✅ Understand both Email Content and CV using AI

✅ Detect the job position the candidate is applying for

✅ Retrieve Job Description from Google Sheets

✅ Extract only job-relevant information

- Full Name
- Email
- Phone Number
- Relevant Experience
- Relevant Skills
- Relevant Education

✅ Compare candidate profile against the Job Description

✅ Calculate an AI similarity score (0–100)

✅ Automatically classify candidates

- 🟢 Interview
- 🟡 Review
- 🔴 Rejected

✅ Save candidate evaluation into Google Sheets

✅ Send professional acceptance or rejection emails

✅ Return structured JSON output

---

# 🏗 Workflow Architecture

```text
                     Gmail Trigger
                           │
                           ▼
                 Read Incoming Email
                           │
                           ▼
                Extract PDF Attachment
                           │
                           ▼
                 Extract CV Text (PDF)
                           │
                           ▼
                 AI Recruitment Agent
                 ┌──────────────┐
                 │              │
                 ▼              ▼
         Job Lookup Tool    Candidate Analysis
                 │              │
                 └──────┬───────┘
                        ▼
               Candidate Evaluation
                        │
                        ▼
               Similarity Score (0-100)
                        │
                        ▼
                 Hiring Decision
                        │
         ┌──────────────┼──────────────┐
         ▼              ▼              ▼
   Interview         Review        Rejected
         │                             │
         ▼                             ▼
 Save Candidate                 Save Candidate
         │                             │
         ▼                             ▼
 Google Sheets                 Google Sheets
         │                             │
         ▼                             ▼
Interview Email               Rejection Email
```

---

# 🧠 AI Evaluation Model

Each candidate is evaluated against the job description using a weighted scoring system.

| Category | Weight |
|----------|--------:|
| Relevant Skills | 50% |
| Relevant Experience | 30% |
| Relevant Education | 20% |

### Final Decision

| Score | Status |
|-------:|--------|
| 80 – 100 | 🟢 Interview |
| 60 – 79 | 🟡 Review |
| 0 – 59 | 🔴 Rejected |

---

# ⚙️ Technologies

- n8n
- OpenAI Compatible Models
- Google Sheets
- Gmail
- PDF Text Extraction
- AI Agent
- JSON Structured Output
- REST APIs

---

# 📂 Google Sheets Structure

## Jobs Sheet

| job_id | job_title | job_description |
|--------|-----------|-----------------|

Example

| JOB-001 | Backend Developer | Python, Django, REST APIs... |
| JOB-002 | Front-End Developer | HTML, CSS, JavaScript, React... |
| JOB-003 | Data Analyst | SQL, Power BI, Python... |

---

## Candidates Sheet

| id | name | email | phone | job_id | score | status |
|----|------|-------|-------|--------|-------|--------|

---

# 🤖 AI Agent Responsibilities

The AI Agent is responsible for:

- Reading email content
- Reading attached CV
- Understanding candidate intent
- Detecting the target job
- Searching the Job Database
- Extracting relevant information only
- Matching candidate qualifications with job requirements
- Calculating similarity score
- Assigning hiring status
- Saving candidate information
- Returning structured JSON

---

# 📁 Project Structure

```text
HireLens-AI/
│
├── workflow/
│   └── hirelens-workflow.json
│
├── docs/
│   ├── workflow.png
│   ├── architecture.png
│   └── screenshots/
│
├── examples/
│   ├── sample-email.txt
│   ├── sample-cv.pdf
│   └── sample-output.json
│
├── .env.example
├── .gitignore
├── LICENSE
└── README.md
```

---

# 🚀 Getting Started

## Clone Repository

```bash
git clone https://github.com/your-username/hirelens-ai.git
```

---

## Import Workflow

Import the workflow JSON into your n8n instance.

---

## Configure Credentials

Configure the following credentials:

- Gmail
- Google Sheets
- AI Model Provider
- Environment Variables

---

## Activate Workflow

Enable the workflow.

Send an email with a PDF CV attached.

The system will automatically:

- Read the email
- Extract the CV
- Detect the applied position
- Retrieve the matching job description
- Evaluate the candidate
- Calculate the score
- Save the result
- Send the appropriate email response

---

# 📊 Example Output

```json
{
  "id": 15,
  "name": "John Doe",
  "email": "john@example.com",
  "phone": "+1 555 123 4567",
  "job_id": "JOB-002",
  "job_title": "Front-End Developer",
  "score": 91,
  "status": "interview"
}
```

---

# 🔮 Future Improvements

- OCR support for scanned CVs
- Multi-language CV parsing
- Duplicate application detection
- ATS integration
- Calendar interview scheduling
- HR Dashboard
- Candidate ranking
- Analytics & Reporting
- Slack Integration
- Microsoft Teams Integration
- WhatsApp Notifications

---

# 📸 Screenshots

> Add screenshots here after completing the project.

- Workflow Overview
- Google Sheets Output
- Candidate Evaluation
- Interview Email
- Rejection Email

---

# 👨‍💻 Author

**Seif**

AI Automation Engineer

- GitHub: https://github.com/seif245
- LinkedIn: https://www.linkedin.com/in/seif-s/

---

# ⭐ Support

If you found this project useful, consider giving it a ⭐ on GitHub.

It helps others discover the project and supports future improvements.

---

# 📄 License

This project is licensed under the **MIT License**.

Feel free to use, modify, and contribute.
