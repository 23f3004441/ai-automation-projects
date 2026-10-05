# AI Lead Engagement & Sales Automation Workflows

This repository contains three independent automation workflows that together cover inbound WhatsApp lead engagement, outbound AI voice qualification, proposal generation, and prospect research.

## Files & Overview

| File | Platform | Purpose |
| :--- | :--- | :--- |
| `WhatsApp_AI_Lead_Response_Assistant.json` | n8n | AI-powered WhatsApp responder for gym/fitness leads |
| `Lead_Qualifier_Voice_Agent_Proposal.json` | Make.com | AI voice qualification, CRM update, and proposal generation |
| `ANALYZE_COMPANY` | Relevance AI | Company intelligence, website scraping, and business model summary |
| `RESEARCH_PROSPECT` | Relevance AI | Prospect LinkedIn profiling, role insights, and key interest analysis |
| `PRE_CALL_REPORT_GENERATOR` | Relevance AI | Pre-call briefing synthesis, talking points, and discovery question generator |

---

## Problems They Solve

Sales teams and small businesses often lose leads because:
- WhatsApp inquiries are answered too slowly or not at all.
- Repetitive questions about pricing, timings, location, and policies consume staff time.
- Spam, personal chats, and group messages get mixed with real leads.
- Leads are not logged consistently in a CRM or spreadsheet.
- Qualified leads are not followed up with a call.
- Proposal creation is manual and slow.
- No-answer follow-ups are forgotten.
- Reps go into calls unprepared due to tedious manual prospect and company research.

These workflows automate the repetitive parts:
- **Instant WhatsApp replies:** AI assistant trained on approved business information answers immediately.
- **Human handoff:** Seamless routing to team members when the AI cannot answer or the lead requests a person.
- **Lead logging:** Automated record creation in Google Sheets and CRM.
- **Owner notifications:** Instant alerts for new, high-intent, or hot leads.
- **AI voice calls:** Autonomous qualification calls for qualified prospects via voice agents.
- **Automated CRM updates:** Real-time logging of call outcomes, notes, and qualification status in Airtable.
- **Instant proposal generation:** Auto-populates and sends PandaDoc proposals when leads show buying interest.
- **Automated follow-ups:** Proactive multi-channel follow-up emails and Slack alerts for unanswered calls.
- **Automated pre-call research:** Deep company and prospect dossiers generated minutes before meetings.

---

## Workflow 1: WhatsApp AI Lead Response Assistant (n8n)

### What it does
Receives WhatsApp messages, filters out groups and duplicates, checks conversation history, asks an LLM for an approved contextual reply, routes the message, sends it back via WhatsApp, logs the lead details in Google Sheets, and notifies the business owner when human intervention or sales attention is needed.

---

## Workflow 2: Lead Qualifier + Voice Agent + Proposal (Make.com)

### What it does
Watches Airtable for qualified leads, researches the company with Gemini, places an AI voice call through Vapi, updates Airtable with the call recording and outcome, and generates a PandaDoc proposal if the lead is interested. If the lead does not answer, it triggers automated follow-up sequences across Slack and email.

---

## Workflow 3: Prospect & Company Research Suite (Relevance AI)

### What it does
Automates account-based research and pre-meeting preparation using three specialized AI tools. It ingests a target company's website domain and a prospect's LinkedIn profile URL, performs automated extraction and analysis, and compiles an executive pre-call brief for sales reps before the meeting.

### Components

#### 1. ANALYZE_COMPANY
- **Input:** Target company website URL / domain.
- **Function:** Scrapes the company website, identifies core products/services, target audience, business model, and value propositions, and delivers a concise executive summary of the business.

#### 2. RESEARCH_PROSPECT
- **Input:** Prospect's LinkedIn profile URL.
- **Function:** Analyzes the prospect's professional background, current role, responsibilities, career trajectory, public posts, and relevant skills to identify key interests and likely pain points.

#### 3. PRE_CALL_REPORT_GENERATOR
- **Input:** Outputs from `ANALYZE_COMPANY` and `RESEARCH_PROSPECT`.
- **Function:** Synthesizes account and lead insights into an actionable pre-call brief, delivering customized conversation starters, tailored value propositions, potential objections, and discovery questions ready for the call.
