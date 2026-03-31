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
- AWS EC2
- Nginx (reverse proxy)
