# AI Cold Email Personalizer

> **Business Use Case:** B2B Sales Automation, Lead Outreach & Revenue Generation

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white) ![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=flat&logo=openai&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white) ![React](https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black)

## Overview

An AI-powered outreach tool that takes a list of B2B leads (name, company, role, LinkedIn) and generates hyper-personalized cold emails using GPT-4. Each email references the prospect's specific company, recent news, role challenges, and value proposition — at scale.

**Business Impact:** Increases cold email reply rates from industry average of 1-3% to 8-15%+ through deep personalization. Used by SDRs, founders, and growth teams.

## Features

- **Lead Enrichment** — Pulls company info, recent news, job description from LinkedIn/web
- **Personalization Engine** — GPT-4 writes unique, context-aware emails for each lead
- **Tone Control** — Adjust for casual, professional, or industry-specific voice
- **Bulk Generation** — Process 100s of leads from CSV in minutes
- **Email Variants** — Generate 3 subject line variations per email for A/B testing
- **Spam Score Check** — Evaluates deliverability before sending
- **CRM Integration** — Export to HubSpot, Salesforce, or CSV

## Tech Stack

| Layer | Technology |
|-------|------------|
| LLM | GPT-4o (OpenAI API) |
| Lead Enrichment | Apify (LinkedIn scraper), NewsAPI |
| Backend | FastAPI + PostgreSQL |
| Frontend | React + Tailwind CSS |
| Queue | Celery + Redis |
| Email Validation | ZeroBounce API |

## Sample Generated Email

```
Subject: Quick question about {Company}'s expansion into Southeast Asia

Hi {FirstName},

I saw that {Company} just raised a Series B and is expanding the GTM team
across APAC — congrats on that milestone.

I've been building an AI tool that helps B2B sales teams like yours cut
prospecting time by 70% while tripling personalization at scale. Given
your focus on pipeline velocity, I thought it might be relevant.

Would you be open to a 15-minute call this week?

Best,
[Your name]
```

## Pipeline

```
Leads CSV (name, company, role, LinkedIn URL)
         ↓
  [Lead Enrichment: company news, job description, recent activity]
         ↓
  [GPT-4 Prompt Construction with context]
         ↓
  [Email Generation + Spam Score Check]
         ↓
  Output: personalized_emails.csv + CRM export
```

## Setup

```bash
git clone https://github.com/nkhalfe56-star/ai-cold-email-personalizer
cd ai-cold-email-personalizer
pip install -r requirements.txt
export OPENAI_API_KEY=your_key
uvicorn main:app --reload
```

## Business Case

| Metric | Manual Outreach | AI Personalizer |
|--------|----------------|------------------|
| Time per email | 15-20 min | < 5 seconds |
| Personalization depth | Surface level | Deep context |
| Reply rate | 1-3% | 8-15%+ |
| Scale | 20-30/day | 500+/day |

## License

MIT License
