AI-Powered Social Media Automation Workflow

This repository contains an end-to-end AI-powered automation workflow built using n8n.

The workflow automatically:
reads article links from Google Sheets,
summarizes articles using AI,
generates LinkedIn and Twitter/X posts,
publishes content automatically to social platforms.

The goal of this project was to explore:
AI workflow automation,
cloud deployment,
OAuth integrations,
API orchestration,
social media automation pipelines.

⚡ Features
✅ Google Sheets Trigger Automation
✅ AI Article Summarization
✅ AI-Generated LinkedIn Posts
✅ AI-Generated Twitter/X Posts
✅ Automated Multi-Platform Posting
✅ OAuth 2.0 Integrations
✅ Cloud Hosted n8n Deployment
✅ Docker + Render Deployment Setup

🛠️ Technologies Used
n8n
Render
Docker
Google AI Studio
Google Cloud Console
LinkedIn Developer Portal
X Developer Portal

🔄 Workflow Flow
Google Sheets Trigger
        ↓
AI Article Summarizer
        ↓
Generate LinkedIn Content
        ↓
Generate Twitter/X Content
        ↓
Auto Publish to Social Platforms

☁️ Deployment Setup

Local n8n Setup
For local deployments, configure environment variables:

N8N_HOST=localhost
N8N_PORT=5678
N8N_PROTOCOL=http
WEBHOOK_URL=http://localhost:5678

Cloud Deployment (Render/Railway)
For cloud-hosted deployments:

N8N_HOST=your-domain.onrender.com
N8N_PROTOCOL=https
WEBHOOK_URL=https://your-domain.onrender.com
N8N_EDITOR_BASE_URL=https://your-domain.onrender.com

Deploy using official n8n Docker image:
docker.io/n8nio/n8n

🔐 OAuth & API Setup
Google Sheets API Setup

Inside Google Cloud Console:

Enable:
Google Sheets API
Google Drive API

Create:
OAuth 2.0 Client
Add OAuth Redirect URL from n8n.

Copy:
Client ID
Client Secret
LinkedIn OAuth Setup

Inside LinkedIn Developer Portal:

Enable:
Share on LinkedIn
Sign In with LinkedIn

Add Redirect URL from n8n.

Copy:

Client ID
Client Secret
Twitter/X OAuth Setup

Inside X Developer Portal:

Configure:
Read and Write permissions
OAuth Redirect URL from n8n

Copy:
Client ID
Client Secret

📥 Importing Workflow
Open n8n
Create New Workflow
Import the provided workflow JSON file
Configure credentials
Activate workflow

📌 Concepts Explored
Workflow Automation
LLM Integration
OAuth 2.0
Docker Deployment
Cloud Hosting
Webhooks
API Integrations
Social Media Automation
AI Content Generation
