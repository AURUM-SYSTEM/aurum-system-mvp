📄 AURUM SYSTEM – MVP SPEC (FIELD REPORTING AI)
1. 📌 Overview
AURUM SYSTEM is an AI-powered field reporting system designed for environments with low connectivity and high operational pressure.
It allows field agents to record voice, text, and media, and automatically transforms them into structured operational reports.
The system targets:
NGOs
Field operations teams
Security teams
Agricultural cooperatives
Administrative field agents
2. 🎯 MVP Objective
The MVP aims to validate:
“Can a field agent generate a structured report from voice input, even in offline conditions, and have it usable by a supervisor?”
3. 👤 User Roles
3.1 Field Agent
Create a field report
Record voice input
Add text notes
Upload photos
Capture GPS location
Work offline
Sync when network is available
3.2 Supervisor
View submitted reports
Validate / review reports
Access dashboard overview
Track field activities
Export reports (PDF)
3.3 Admin
Manage users
Manage organizations
Assign roles
4. 🔄 Core User Flow (IMPORTANT)
Field Agent Flow
Open mobile app
Select “New Report”
Record voice OR write text
Add photos (optional)
GPS auto-captured
Save locally (offline-first)
Sync when network is available
Backend Processing Flow
Receive raw input (audio/text/images)
Transcribe audio (speech-to-text)
Structure data using AI (GPT)
Store structured report
Make available in dashboard
Enable PDF export
5. 🧠 Core Features (MVP)
5.1 Voice-to-Text
Audio recording in mobile app
Transcription using AI (Whisper or equivalent)
5.2 AI Report Structuring
Transforms raw input into:
title
category
description
key findings
metadata (time, location, agent)
5.3 Offline Mode (CRITICAL)
Local storage on device
Queue system for unsent reports
Automatic sync when internet returns
No data loss in offline mode
5.4 Synchronization System
Incremental sync (only new data sent)
Retry mechanism for failed uploads
Conflict-safe updates (server authority model for MVP)
5.5 Dashboard (Web)
List of reports
Filters (agent, date, category)
Basic statistics
Map view (GPS points)
Report preview
5.6 Export
PDF report generation per submission
6. 🧱 Data Model (Simplified)
User
id
name
role
organization
Report
id
agent_id
text_raw
text_structured
audio_url
images[]
gps_location
status (pending/synced/validated)
created_at
7. ⚙️ Technical Stack (Suggested)
Frontend (Mobile)
React Native (or Flutter)
Local storage (SQLite / AsyncStorage)
Backend
Node.js (Express or NestJS)
REST API
Database
MongoDB or PostgreSQL
AI Services
Speech-to-text API (Whisper)
LLM (GPT or equivalent)
Dashboard
React.js / Next.js
8. 🔌 Offline Architecture (Key Requirement)
Mobile app stores all reports locally
Each report has a sync status:
pending
synced
failed
Sync triggers when:
internet available
app opened
background sync
9. ⚠️ Scope Control (MVP ONLY)
Included:
Voice capture
Text reports
Photo upload
GPS capture
Offline mode
Sync system
Basic dashboard
AI structuring
NOT included (later phases):
Advanced AI insights
Predictive analytics
Multi-module system (AGRO/HEALTH/GOV)
Complex conflict resolution system
Real-time streaming sync
10. 📊 Success Criteria
MVP is successful if:
An agent can create a report offline
Data syncs correctly to backend
Supervisor can view reports in dashboard
AI generates structured reports usable without editing
11. 🚀 Vision (short)
AURUM SYSTEM aims to become a unified field intelligence infrastructure for emerging markets, enabling structured decision-making from raw field data.