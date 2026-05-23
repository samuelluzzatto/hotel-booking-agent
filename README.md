# 🤖 Autonomous Hotel Booking Agent — AI + n8n + WhatsApp

> Autonomous AI agent that handles the full hotel sales and booking process via WhatsApp — without human intervention.

---

## 📊 Results in Production

| Metric | Result |
|--------|--------|
| Booking rate | **+30% increase** |
| Operational cost | **-60% reduction** |
| Human intervention | **Zero** in the sales flow |

---

## 🧠 What This Agent Does

A guest sends a message on WhatsApp. From that point, the agent handles everything:

```
Guest message on WhatsApp
        ↓
Agent greets and qualifies (check-in, check-out, guests)
        ↓
Checks availability on PMS (Stays)
        ↓
Collects guest data (name, document, contact)
        ↓
Saves data to database (SQL)
        ↓
Generates and sends payment link
        ↓
Confirms payment automatically
        ↓
Creates reservation on PMS with all guest info
        ↓
Sends booking confirmation to guest
```

**No human involved. No manual step. Full cycle in minutes.**

---

## 🛠️ Tech Stack

| Tool | Role |
|------|------|
| **n8n** | Automation engine and agent orchestration |
| **GPT-4 (OpenAI API)** | Natural language understanding and response generation |
| **WhatsApp Business API** | Guest communication channel |
| **Stays PMS** | Hotel property management system integration |
| **SQL** | Guest data and booking storage |
| **Kommo CRM** | Lead tracking and follow-up |

---

## 🏗️ Architecture Overview

```
┌─────────────────────────────────────────────────┐
│                  WhatsApp API                    │
│           (incoming guest messages)              │
└──────────────────────┬──────────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────────┐
│                    n8n Engine                    │
│  ┌─────────────┐  ┌──────────┐  ┌────────────┐  │
│  │  GPT-4 Node │  │ SQL Node │  │ HTTP/API   │  │
│  │ (NLP + AI)  │  │ (Storage)│  │ (Payments) │  │
│  └─────────────┘  └──────────┘  └────────────┘  │
└──────────────────────┬──────────────────────────┘
                       │
          ┌────────────┴────────────┐
          ▼                         ▼
┌─────────────────┐       ┌─────────────────────┐
│   Stays PMS     │       │   Payment Gateway   │
│ (auto-creates   │       │  (link generation + │
│  reservation)   │       │   confirmation)     │
└─────────────────┘       └─────────────────────┘
```

---

## 💡 Key Features

- **Fully autonomous** — handles objections, questions, and edge cases via GPT-4
- **Real-time availability check** — queries PMS before confirming any booking
- **Automated payment flow** — generates link, monitors confirmation, updates reservation
- **Structured data collection** — validates guest info before writing to database
- **PMS sync** — reservation created automatically with all guest details
- **24/7 operation** — no business hours, no delays, no human bottleneck

---

## 📁 Repository Structure

```
hotel-booking-agent/
├── flows/
│   └── hotel_agent_flow.json     # n8n workflow (export)
├── docs/
│   ├── architecture.md           # Detailed architecture notes
│   └── setup.md                  # How to configure and deploy
├── database/
│   └── schema.sql                # Database schema
└── README.md
```

---

## 🚀 How to Run

1. Import `flows/hotel_agent_flow.json` into your n8n instance
2. Configure credentials:
   - OpenAI API Key (GPT-4)
   - WhatsApp Business API token
   - Stays PMS API Key
   - Database connection (SQL)
   - Payment gateway credentials
3. Activate the workflow
4. Test with a WhatsApp message to your business number

---

## 📬 About the Developer

Built by **Samuel Luzzatto** — AI Automation Developer specialized in autonomous agents and end-to-end workflow automation.

- 🔗 [LinkedIn](https://www.linkedin.com/in/samuelluzzatto)
- 📧 luzzattoribeiro@gmail.com
- 🌍 Open to remote opportunities · Brazil & international (PT / DE / EN)

---

*This project is part of a production system. Sensitive credentials and client data are not included in this repository.*
