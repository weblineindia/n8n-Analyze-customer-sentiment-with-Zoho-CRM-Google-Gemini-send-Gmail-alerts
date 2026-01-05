
# Analyze Customer Sentiment with Zoho CRM, Google Gemini & Gmail Alerts

This n8n workflow automatically analyzes newly created **Notes** in Zoho CRM using **AI-powered sentiment analysis** (Google Gemini or similar LLM). It updates the related CRM records with **sentiment labels and scores**, and sends **Gmail alerts** whenever negative sentiment is detected — giving teams real-time visibility into customer dissatisfaction and potential risks.

---

## 🚀 Quick Start – Setup Steps

1. Connect **Zoho CRM OAuth2** credentials in n8n
2. In Zoho CRM, create two custom fields in the parent module:

   * `Sentiment_Label`
   * `Sentiment_Score`
3. Add your **AI provider credentials** (Google Gemini API key or equivalent)
4. Configure **Gmail OAuth2** credentials and set alert recipients
5. Activate the workflow and test it by creating a new Note in Zoho CRM

---

## 📌 What It Does

This workflow automates sentiment monitoring inside Zoho CRM by:

* Periodically checking for **new or updated Notes**
* Extracting note text and metadata (note ID, parent ID, module name)
* Sending note content to an **AI model** for sentiment analysis
* Classifying sentiment as **Positive**, **Neutral**, or **Negative**
* Generating a **numeric sentiment score**
* Updating the related CRM record with sentiment results
* Sending **instant Gmail alerts** when negative sentiment is detected

This helps teams identify unhappy customers early and take action before issues escalate.

---

## 👥 Who’s It For

Ideal for:

* Customer support teams monitoring feedback tone
* Sales teams tracking customer interaction sentiment
* CRM administrators implementing AI automation
* Customer success managers detecting churn signals
* Businesses using Zoho CRM that want sentiment intelligence

---

## 🛠 Requirements

* n8n instance (cloud or self-hosted)
* Zoho CRM OAuth2 credentials with access to:

  * Notes
  * Parent CRM modules (Leads, Deals, Contacts, etc.)
* AI provider credentials (Google Gemini or similar LLM)
* Gmail OAuth2 credentials
* Two Zoho CRM custom fields:

  * `Sentiment_Label`
  * `Sentiment_Score`

---

## ⚙️ How It Works

### 1. Schedule Trigger

Runs at a configured interval to check for newly created or updated Notes.

### 2. Fetch Latest Note

Retrieves the most recent Note from Zoho CRM.

### 3. Extract Note Details

Pulls:

* Note text
* Note ID
* Parent record ID
* Parent module name

### 4. AI Sentiment Analysis

The note text is analyzed by the AI model, returning:

* Sentiment label
* Sentiment score

### 5. Conditional Routing

* **Negative sentiment**

  * Sends a Gmail alert
  * Updates CRM sentiment fields
* **Positive / Neutral sentiment**

  * Updates CRM sentiment fields only

### 6. CRM Update

Writes sentiment label and score back to the parent record for reporting and tracking.

---

## 🛠 Customization Options

* **AI Prompt**

  * Adjust sentiment definitions
  * Add emotion tags or confidence levels
* **CRM Field Mapping**

  * Rename or remap sentiment fields
* **Alert Logic**

  * Change thresholds for what counts as “negative”
* **Email Templates**

  * Customize subject, body, and recipients
* **Schedule Frequency**

  * Run more frequently for high-activity CRMs

---

## ➕ Optional Enhancements

* Slack or Microsoft Teams alerts
* Historical sentiment logging in Google Sheets or Airtable
* Weekly or monthly sentiment summary emails
* Auto-create CRM tasks for critical notes
* Priority escalation based on sentiment score
* Trend analysis dashboards

---

## 📈 Use Case Examples

1. Alert managers about negative support interactions
2. Track sentiment trends across sales conversations
3. Identify churn risks early
4. Measure relationship health over time
5. Escalate critical customer issues automatically

---

## 🧪 Troubleshooting Guide

| Issue                  | Possible Cause                 | Solution                                    |
| ---------------------- | ------------------------------ | ------------------------------------------- |
| Sentiment not updating | Custom fields missing          | Add `Sentiment_Label` and `Sentiment_Score` |
| Note not detected      | Fetch logic too narrow         | Increase schedule frequency or widen query  |
| AI output invalid      | Prompt or model error          | Refine prompt or verify AI credentials      |
| Gmail alert not sent   | OAuth expired or misconfigured | Reconnect Gmail credentials                 |
| Incorrect sentiment    | Weak prompt instructions       | Improve sentiment definitions in prompt     |

---

## 💬 Need Help?

Need help setting up, extending, or scaling this workflow — including advanced AI scoring, dashboards, or multi-channel alerts?

**WeblineIndia** provides expert n8n automation services to help you build reliable, AI-driven CRM workflows tailored to your business.

---
