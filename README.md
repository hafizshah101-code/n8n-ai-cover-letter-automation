AI Cover Letter Generator (n8n + Gemini + Adobe PDF Services)

Generate personalized, ATS-friendly cover letters automatically using AI.

This project automates the process of creating tailored cover letters by combining a candidate's resume with a target job description. Users simply upload their resume, paste a job description, and receive a customized cover letter via email within minutes.

Architecture

Workflow Diagram

```text
User
 │
 ▼
Landing Page (Tally)
 │
 ▼
Railway
 │
 ▼
n8n Webhook
 │
 ▼
Adobe PDF Services API
 │
 ▼
Extract Resume Text
 │
 ▼
Google Gemini AI
 │
 ▼
Generate Tailored Cover Letter
 │
 ▼
Gmail API
 │
 ▼
User receives Cover Letter
```


![Architecture](aws-cloudopsmonitoring-architecture.png)



##Features

Upload resume as PDF
Paste any job description
Automatically extracts resume text using Adobe PDF Services API
Uses Google Gemini AI to generate personalized cover letters
Sends generated cover letter directly to the user's email
Fully automated using n8n
Hosted on Railway

##Tech Stack

| Technology             | Purpose                    |
| ---------------------- | -------------------------- |
| n8n                    | Workflow Automation        |
| Google Gemini          | AI Cover Letter Generation |
| Adobe PDF Services API | Resume Text Extraction     |
| Gmail API              | Email Delivery             |
| Tally Forms            | User Input Form            |
| Railway                | Workflow Hosting           |



##Workflow

1. User Submission

The user fills out the landing page with:

Name
Email
Target Job Description
Resume (PDF)

2. Webhook Trigger

The Tally form sends the submission to an n8n Webhook which starts the automation.

3. Resume Processing

The workflow:

Authenticates with Adobe PDF Services
Uploads the PDF
Extracts all resume text
Downloads extracted JSON

4. AI Generation

Google Gemini receives:

Resume content
Job description

The AI is instructed to:

Never invent experience
Never invent certifications
Never invent projects
Preserve factual information
Improve grammar
Improve wording
Produce a professional cover letter

5. Email Delivery

The generated cover letter is emailed directly to the candidate using Gmail.

##AI Prompt Strategy

The workflow compares:

Candidate Resume
Target Job Description

The AI then generates a cover letter that:

Matches relevant skills
Highlights transferable experience
Uses professional language
Maintains factual accuracy
Optimizes readability for ATS systems

##Deployment

The automation is deployed on Railway, where the n8n application runs as a managed service backed by a persistent PostgreSQL database.

Infrastructure
Railway Cloud Platform
n8n (Production Instance)
PostgreSQL Database
HTTPS Webhook Endpoint
Persistent Workflow Storage
Automatic Restarts & Deployment

This architecture enables reliable execution, secure credential storage, and persistent workflow history while minimizing infrastructure management.


##Future Improvements
Support DOCX resumes
Generate multiple cover letter styles
Download as PDF
ATS score analysis
Resume optimization suggestions
Multi-language support

## 💼 Skills Demonstrated

This project showcases practical skills across automation, cloud deployment, and AI integration:

Workflow Automation (n8n)
Cloud Deployment (Railway)
PostgreSQL Database Management
REST API Integration
AI Prompt Engineering
Google Gemini API
Adobe PDF Services API
Gmail API Integration
Webhook Development
PDF Processing
JSON Data Transformation
Low-Code/No-Code Automation
SaaS Integration
Production Deployment
Event-Driven Architecture
