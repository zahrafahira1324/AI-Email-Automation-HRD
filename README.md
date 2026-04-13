# 🤖 AI Email Automation for HR Recruitment

## 📌 Overview
AI-powered workflow untuk mengotomatisasi proses screening CV dari email menggunakan n8n dan NLP.

## 🚨 Problem
Screening CV manual memakan waktu lama, tidak konsisten, dan memperlambat proses rekrutmen.

## 💡 Solution
Membangun sistem automation yang:
- Mengambil email kandidat otomatis
- Mengekstrak CV
- Mengklasifikasikan kandidat dengan AI
- Memberikan skor kelayakan
- Mengirim email response otomatis
- Menyimpan data ke Google Sheets

## 🧠 Workflow
Email → n8n → CV Parsing → AI Classification → Scoring → Auto Response → Google Sheets

## ⚙️ Tech Stack
- n8n
- AI Agent (NLP)
- IMAP / SMTP
- Google Sheets

## 📊 Impact
- Mempercepat proses screening
- Mengurangi beban kerja HR
- Respon kandidat lebih cepat

## 📄 Documentation
Full documentation available here:
[Download Report](./AI_Email_Automation_HRD_Report.pdf)

## 🧠 Workflow Architecture

```mermaid
flowchart TD
    A[Candidate Email] --> B[Email Trigger]
    B --> C[CV Parsing]
    C --> D[AI Classification]
    D --> E[Scoring]
    E --> F{Decision}

    F -->|Pass| G[Interview Email]
    F -->|Fail| H[Rejection Email]

    G --> I[Store Data]
    H --> I
    I --> J[📈 Logging & Monitoring]
