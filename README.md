# nous-n8nchat

AI-powered lead capture and qualification workflow built with **n8n**, **Google Gemini**, and **Google Sheets**, designed to run as a webhook-based automation service.

This project enables developers and agencies to deploy an automated chat processing pipeline that captures user messages, analyzes intent using AI, and stores high-intent leads automatically.

---

# Overview

`nous-n8nchat` is a lightweight automation backend that turns incoming messages into structured lead data.

It is designed for:

* AI chat funnels
* landing page lead capture
* automated qualification
* CRM intake pipelines
* agency automation systems

The workflow receives a message via webhook, processes it with an AI agent, determines if the user shows strong buying intent, and saves qualified leads to Google Sheets.

---

# Architecture

High-level workflow:

Webhook → AI Agent → Intent Evaluation → Lead Storage → Response

System components:

* **n8n workflow engine**
* **Google Gemini Chat Model**
* **Conversation memory**
* **Structured output parser**
* **Google Sheets lead database**
* **Webhook response endpoint**

---

# Project Structure

```
nous-n8nchat
│
├ docker-compose.yml
├ Dockerfile
├ README.md
└ workflows
    └ workflow.json
```

---

# Features

• AI-powered intent detection
• webhook-based message ingestion
• automatic lead qualification
• structured AI output parsing
• Google Sheets integration
• deployable in minutes

---

# Use Cases

This system can power:

* AI landing pages
* chatbot funnels
* automated sales qualification
* marketing lead capture
* automation agencies

Typical flow:

1. User submits a message on a landing page
2. Request hits the webhook
3. AI analyzes the conversation
4. System checks for **high purchase intent**
5. Qualified leads are stored automatically

---

# Local Development

Clone the repository:

```bash
git clone https://github.com/alexbecerradev/nous-n8nchat.git
cd nous-n8nchat
```

Start the service:

```bash
docker-compose up
```

Access n8n:

```
http://localhost:5678
```

---

# Deployment (Render)

This project is designed to run easily on **Render**.

Steps:

1. Create a **New Web Service**
2. Connect the GitHub repository
3. Select **Docker environment**

Configuration:

```
Port: 5678
```

Recommended environment variables:

```
N8N_HOST=0.0.0.0
N8N_PORT=5678
N8N_PROTOCOL=https
WEBHOOK_URL=https://yourapp.onrender.com/
N8N_SECURE_COOKIE=false
GENERIC_TIMEZONE=UTC
```

---

# Import the Workflow

Once n8n is running:

1. Open the n8n dashboard
2. Click **Import Workflow**
3. Upload:

```
workflows/workflow.json
```

---

# Example Webhook Request

POST request example:

```json
{
  "message": "Hi, I want pricing information",
  "name": "John",
  "email": "john@email.com"
}
```

The system will:

1. analyze the message with AI
2. detect purchase intent
3. store the lead if qualified
4. return an automated response

---

# Tech Stack

* n8n
* Google Gemini
* Docker
* Render
* Google Sheets API

---

# License

MIT License

---

# Author

Built by the **Nous Automation** team.

Automation infrastructure for modern AI-driven businesses.
