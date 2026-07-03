# 🚀 AI-Powered Social Media Automation Workflow

This repository contains an end-to-end AI-powered automation workflow built using n8n.

The workflow automatically:

- reads article links from Google Sheets
- summarizes articles using AI
- generates LinkedIn and Twitter/X posts
- publishes content automatically to social platforms

The goal of this project was to explore:

- AI workflow automation
- cloud deployment
- OAuth integrations
- API orchestration
- social media automation pipelines

---

# ⚡ Features

- ✅ Google Sheets Trigger Automation
- ✅ AI Article Summarization
- ✅ AI-Generated LinkedIn Posts
- ✅ AI-Generated Twitter/X Posts
- ✅ Automated Multi-Platform Posting
- ✅ OAuth 2.0 Integrations
- ✅ Cloud Hosted n8n Deployment
- ✅ Docker + Render Deployment Setup

---

# 🛠️ Technologies Used

- n8n
- Render
- Docker
- Google AI Studio
- Google Cloud Console
- LinkedIn Developer Portal
- X Developer Portal

---

# 🔄 Workflow Flow

```text
Google Sheets Trigger
        ↓
Optional Xquik Source Context
        ↓
AI Article Summarizer
        ↓
Generate LinkedIn Content
        ↓
Generate Twitter/X Content
        ↓
Auto Publish to Social Platforms
```

## Optional Xquik Source Context

For posts that should respond to current X/Twitter discussion, add an n8n HTTP
Request node between Google Sheets and the article summarizer.

Recommended node fields:

```text
Method: GET
URL: https://xquik.com/api/v1/x/tweets/search
Header: X-API-Key = {{$env.XQUIK_API_KEY}}
Query: q = {{$json.newslinks || $json.topic || $json.keyword}}
Query: limit = 5
```

Map each result's tweet text, author, URL, and timestamp into the summarizer
prompt as source evidence. Keep the existing LinkedIn and X publish nodes
unchanged, and review generated rows or run against a test account before
activating automatic posting.

---

# ☁️ Deployment Setup

## Local n8n Setup

For local deployments, configure environment variables:

```env
N8N_HOST=localhost
N8N_PORT=5678
N8N_PROTOCOL=http
WEBHOOK_URL=http://localhost:5678
```

---

## Cloud Deployment (Render/Railway)

For cloud-hosted deployments:

```env
N8N_HOST=your-domain.onrender.com
N8N_PROTOCOL=https
WEBHOOK_URL=https://your-domain.onrender.com
N8N_EDITOR_BASE_URL=https://your-domain.onrender.com
```

Deploy using official n8n Docker image:

```text
docker.io/n8nio/n8n
```

---

# 🔐 OAuth & API Setup

## Google Sheets API Setup

Inside Google Cloud Console:

Enable:
- Google Sheets API
- Google Drive API

Create:
- OAuth 2.0 Client

Add OAuth Redirect URL from n8n.

Copy:
- Client ID
- Client Secret

---

## LinkedIn OAuth Setup

Inside LinkedIn Developer Portal:

Enable:
- Share on LinkedIn
- Sign In with LinkedIn

Add Redirect URL from n8n.

Copy:
- Client ID
- Client Secret

---

## Twitter/X OAuth Setup

Inside X Developer Portal:

Configure:
- Read and Write permissions
- OAuth Redirect URL from n8n

Copy:
- Client ID
- Client Secret

---

# 📥 Importing Workflow

1. Open n8n
2. Create New Workflow
3. Import the provided workflow JSON file
4. Configure credentials
5. Activate workflow

---

# 📌 Concepts Explored

- Workflow Automation
- LLM Integration
- OAuth 2.0
- Docker Deployment
- Cloud Hosting
- Webhooks
- API Integrations
- Social Media Automation
- AI Content Generation
