# Analyze Customer Sentiment with Zoho CRM, Google Gemini & Send Gmail Alerts

This workflow automatically analyzes newly created **Notes** in Zoho CRM for customer sentiment using an AI model, updates the related CRM records with sentiment labels and scores, and sends **Gmail alerts** whenever negative tone is detected — giving teams real‑time visibility into customer emotions and potential risks. :contentReference[oaicite:1]{index=1}

---

## 🚀 Quick Start – Setup Steps

1. **Connect Zoho CRM OAuth2 credentials** to n8n. :contentReference[oaicite:2]{index=2}
2. In Zoho CRM, add two custom fields (e.g., `Sentiment_Label` and `Sentiment_Score`) to the module where Notes are stored. :contentReference[oaicite:3]{index=3}
3. Add your **AI provider credentials** (Google Gemini API key or other AI model). :contentReference[oaicite:4]{index=4}
4. Configure **Gmail OAuth2** credentials; set the recipient’s email for alerts. :contentReference[oaicite:5]{index=5}
5. Activate the workflow and test it by creating a Note in Zoho CRM. :contentReference[oaicite:6]{index=6}

---

## 📌 What It Does

This workflow automates CRM sentiment tracking by:

- Periodically checking for new or updated Notes in Zoho CRM. :contentReference[oaicite:7]{index=7}
- Extracting text and metadata (note text, note ID, parent ID, module name). :contentReference[oaicite:8]{index=8}
- Sending the text to an AI model (e.g., Google Gemini) for **sentiment analysis**. :contentReference[oaicite:9]{index=9}
- Classifying sentiment as **Positive, Neutral, or Negative**, and generating a numeric score. :contentReference[oaicite:10]{index=10}
- Updating the related CRM record with the sentiment label and score. :contentReference[oaicite:11]{index=11}
- Sending a **Gmail alert** when negative sentiment is detected — helping teams act quickly on critical customer interactions. :contentReference[oaicite:12]{index=12}

This automation helps sales, support, and success teams detect issues early and respond to unhappy customers efficiently. :contentReference[oaicite:13]{index=13}

---

## 👥 Who’s It For

This workflow is ideal for:

- Support teams tracking customer feedback tone. :contentReference[oaicite:14]{index=14}
- Sales teams monitoring interaction sentiment. :contentReference[oaicite:15]{index=15}
- CRM administrators implementing automation. :contentReference[oaicite:16]{index=16}
- Customer success managers detecting early churn signals. :contentReference[oaicite:17]{index=17}
- Businesses that want AI‑driven sentiment tracking in Zoho CRM. :contentReference[oaicite:18]{index=18}

---

## 🛠 Requirements

To use this workflow, you need:

- An **n8n instance** (cloud or self‑hosted). :contentReference[oaicite:19]{index=19}
- **Zoho CRM OAuth2** credentials with permissions to read Notes and update parent records. :contentReference[oaicite:20]{index=20}
- **AI provider credentials** (Google Gemini API key or similar model). :contentReference[oaicite:21]{index=21}
- **Gmail OAuth2 credentials** for sending alerts. :contentReference[oaicite:22]{index=22}
- Two custom fields in Zoho CRM (e.g., `Sentiment_Label` and `Sentiment_Score`). :contentReference[oaicite:23]{index=23}

---

## ⚙️ How It Works & Setup

### 1. **Schedule Trigger**

A schedule trigger periodically initiates the workflow to check for new or updated Notes. :contentReference[oaicite:24]{index=24}

### 2. **Fetch Latest Note**

The workflow retrieves the latest modified Note from Zoho CRM. :contentReference[oaicite:25]{index=25}

### 3. **Extract Note Details**

It extracts key details such as the Note text, note ID, parent record ID, and module name. :contentReference[oaicite:26]{index=26}

### 4. **AI Sentiment Analysis**

The text is sent to the AI model for sentiment classification (Positive, Neutral, Negative) along with a sentiment score. :contentReference[oaicite:27]{index=27}

### 5. **Conditional Routing**

- If the sentiment is **Negative**:
  - A **Gmail alert** is sent.
  - The CRM parent record is updated with sentiment info. :contentReference[oaicite:28]{index=28}
- If not negative:
  - Only the CRM fields are updated. :contentReference[oaicite:29]{index=29}

### 6. **CRM Update**

Sentiment label and score are written back into the parent CRM record to help teams track interaction quality. :contentReference[oaicite:30]{index=30}

---

## 🛠 How to Customize

- **Adjust the AI prompt** — Modify the sentiment analysis prompt to tailor classification style (e.g., add emotion tags). :contentReference[oaicite:31]{index=31}
- **Change CRM field mapping** — Update Zoho CRM field names for your schema. :contentReference[oaicite:32]{index=32}
- **Customize Gmail alerts** — Change email subject, body template, and recipients. :contentReference[oaicite:33]{index=33}
- **Schedule frequency** — Modify the schedule trigger interval to check more or less often. :contentReference[oaicite:34]{index=34}
- **Add metadata** — Extend sentiment output with emotion tags or confidence scores. :contentReference[oaicite:35]{index=35}

---

## ➕ Add‑Ons (Optional Enhancements)

- **Slack or Teams alerts** for negative sentiment in addition to Gmail. :contentReference[oaicite:36]{index=36}
- **Historical sentiment logging** into Google Sheets or Airtable. :contentReference[oaicite:37]{index=37}
- **Weekly sentiment summaries** sent to a team channel. :contentReference[oaicite:38]{index=38}
- **Auto‑task creation** for critical or repetitive negative interactions. :contentReference[oaicite:39]{index=39}
- **Priority escalation logic** based on sentiment score thresholds. :contentReference[oaicite:40]{index=40}

---

## 📈 Use Case Examples

1. Detect and alert on negative customer support interactions. :contentReference[oaicite:41]{index=41}
2. Monitor sentiment trends across sales communications. :contentReference[oaicite:42]{index=42}
3. Escalate unhappy customer cases before churn. :contentReference[oaicite:43]{index=43}
4. Track CRM sentiment score over time for quality insights. :contentReference[oaicite:44]{index=44}
5. Provide automated alerts to managers when sentiment drops below thresholds. :contentReference[oaicite:45]{index=45}

---

## 🧪 Troubleshooting Guide

| **Issue**              | **Possible Cause**           | **Solution**                                              |
| ---------------------- | ---------------------------- | --------------------------------------------------------- | --------------------------------------- |
| Sentiment not updating | Missing custom CRM fields    | Add `Sentiment_Label` and `Sentiment_Score` fields in CRM |
| Note not detected      | Only the latest note fetched | Increase schedule frequency or broaden fetch logic        |
| AI output invalid      | Prompt or model error        | Adjust prompt or check AI credentials                     |
| Gmail alert not sent   | Gmail OAuth expired          | Reconnect Gmail credentials                               |
| Incorrect sentiment    | Weak prompt instructions     | Refine the AI prompt wording                              | :contentReference[oaicite:46]{index=46} |

---

## 💬 Need Help?

If you need help configuring, customizing, or extending this workflow — from advanced AI scoring to multi‑channel alerts — the **WeblineIndia** n8n automation specialists can assist you with tailored solutions and integration guidance. :contentReference[oaicite:47]{index=47}

---
