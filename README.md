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
Lihat detail lengkap di file `report.pdf`

## 🧠 Workflow Architecture

```mermaid
flowchart TD
    A[Candidate Email (CV PDF)] --> B[Email Trigger (IMAP - n8n)]
    B --> C[CV Extraction and Parsing]

    C -->|Success| D[AI Classification]
    C -->|Fail| X[Log Error]

    D --> E[Candidate Scoring]
    E --> F{Decision Engine}

    F -->|Qualified| G[Send Interview Invitation]
    F -->|Not Qualified| H[Send Rejection Email]

    G --> I[Store to Google Sheets]
    H --> I

    I --> J[Logging and Monitoring]

    I --> J[📈 Logging & Monitoring]
