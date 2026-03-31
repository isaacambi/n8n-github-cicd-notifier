# GitHub CI/CD Notifier with AI Commit Classifier

## Overview
An automated CI/CD notification system built with n8n that monitors 
a GitHub repository for push events and delivers intelligent 
notifications to Slack and Gmail — powered by Groq AI.

Every time code is pushed to the repository, this workflow:
- Detects the push event via GitHub Webhook
- Extracts key information (pusher, branch, commit message, repo name)
- Sends the commit message to Groq AI (LLaMA 3.3 70B) for classification
- Classifies the commit as: Feature, Bug Fix, Security Update, or Maintenance
- Delivers a detailed AI analysis report to both Slack and Gmail simultaneously

## Tech Stack
- n8n (workflow automation)
- GitHub Webhooks
- Groq AI (LLaMA 3.3 70B)
- Slack API
- Gmail API
- Docker

## Workflow Architecture
```
GitHub Push → Webhook → Edit Fields → HTTP Request (Groq AI)
                                              ↓              ↓
                                           Slack          Gmail
```

## How It Works

1. **GitHub Webhook** — Listens for push events on the repository
2. **Edit Fields Node** — Extracts pusher name, branch, commit message and repo name from the payload
3. **HTTP Request Node** — Sends the commit message to Groq AI (LLaMA 3.3 70B) with a prompt to classify it
4. **Slack Node** — Sends the AI classification result to the devops channel
5. **Gmail Node** — Sends a detailed email report to the team inbox

## Screenshots

### n8n Workflow Canvas
![Workflow Canvas](screenshots/workflow-canvas.png)

### GitHub Webhook Configuration
![GitHub Webhook](screenshots/github-webhook.png)

### Slack Notification
![Slack Message](screenshots/slack-message.png)

### Gmail Notification
![Gmail Email](screenshots/gmail-email.png)

## What I Learned
- Setting up GitHub Webhooks and connecting to n8n
- Extracting and mapping data from webhook payloads
- Integrating Groq AI for intelligent commit classification
- Parallel node execution in n8n
- Deploying n8n on AWS EC2 with Docker and Nginx reverse proxy

## Author
Isaac Ambi — DevOps & Cloud Engineer

