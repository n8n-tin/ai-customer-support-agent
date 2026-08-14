# 🤖 AI Customer Support & Lead Management Automation

An AI-powered customer support and lead qualification automation built with n8n and Google Gemini.

The workflow helps businesses respond to customer inquiries, identify when human intervention is required, qualify leads, prioritize high-value opportunities, and record customer interactions in a CRM.

---

## 📌 Business Problem

Customer inquiries often require manual handling, which can lead to:

- Slow response times
- Inconsistent answers
- Missed sales opportunities
- Manual lead qualification
- Difficulty identifying high-priority customers
- Lack of a structured escalation process

The goal of this project was to automate the initial customer support and lead qualification process while keeping human intervention available when needed.

---

## 💡 Solution

I designed an AI-powered workflow that:

1. Captures customer inquiries
2. Retrieves information from a controlled Knowledge Base
3. Generates an AI-powered response
4. Determines whether human escalation is required
5. Qualifies the customer lead
6. Scores the lead
7. Identifies high-priority opportunities
8. Notifies the appropriate team
9. Records the interaction in a CRM
10. Provides an error-handling workflow for monitoring failures


---
## 🔄 Process Map

```text
Customer Inquiry
       ↓
Capture Customer Data
       ↓
Retrieve Knowledge Base
       ↓
Generate AI Response
       ↓
Check Human Escalation
       ↓
   ┌───┴───┐
   ↓       ↓
  YES      NO
   ↓       │
Email      │
Support    │
   ↓       │
   └───┬───┘
       ↓
Qualify Lead
       ↓
Evaluate Lead
       ↓
High Priority?
       ↓ YES
Notify Sales Team
       ↓
     CRM
```


## ⚙️ How the Workflow Works

1. Customer Inquiry

The workflow receives a customer question or request.

2. Capture Customer Data

Customer information and the inquiry are captured for processing and record keeping.

3. Retrieve Knowledge Base

The workflow retrieves information from a controlled Google Docs Knowledge Base.

This helps keep AI responses grounded in approved business information.

4. Generate AI Response

Google Gemini generates a customer-facing response based on the available Knowledge Base information.

5. Check Human Escalation

The workflow determines whether the inquiry requires human intervention.

If escalation is required:

Human Escalation = YES
        ↓
Email Support Team

If escalation is not required:

Human Escalation = NO
        ↓
Continue to Lead Qualification

Both paths continue to lead qualification.

6. Qualify Lead

The AI evaluates the customer inquiry and produces structured lead information.

Example:

```json
{
  "intent": "Purchase Intent",
  "lead_score": 90,
  "priority": "High"
}
```

7. Evaluate Lead

The workflow applies business logic to determine whether the lead is high priority.

8. Notify Sales Team

High-priority leads trigger an internal notification so the appropriate team can follow up.

9. CRM

Customer and lead information is recorded in Google Sheets as the CRM layer.

---

## 🧠 AI Capabilities

The workflow uses structured AI output to support business decisions.

The AI can determine:

Customer intent
Lead score
Lead priority
Whether human escalation is required
Appropriate customer responses

Structured output helps the workflow reliably pass AI results into downstream automation logic.

---

## 🛡️ Human Escalation

The automation does not attempt to answer every question automatically.

When the workflow determines that human assistance is required, it sends an internal email notification.

This creates a human-in-the-loop approach:

AI handles routine inquiries
          ↓
Complex / uncertain inquiry
          ↓
Human escalation
          ↓
Support team intervention

---

## 🚨 Error Handling

A separate Error Handler workflow has been configured to monitor workflow failures.

Workflow Error
      ↓
Error Trigger
      ↓
Capture Error Details
      ↓
Gmail Notification

The error notification includes information such as:

Execution ID
Error message
Last node executed
Execution URL

This provides visibility into automation failures and supports troubleshooting.

---

## 📸 Workflow Screenshots

### n8n Automation Workflow

The complete n8n workflow demonstrates the end-to-end customer support and lead management automation.

![AI Customer Support & Lead Management Workflow](https://github.com/n8n-tin/ai-customer-support-agent/blob/main/screenshots/workflow-final.png)

### CRM Test Results

The workflow records customer inquiries, AI responses, lead scores, intent, priority, and human escalation status in Google Sheets.

![CRM Test Results](https://github.com/n8n-tin/ai-customer-support-agent/blob/main/screenshots/crm-test-results.png)

### High-Priority Lead Notification

High-priority leads automatically trigger an internal notification for follow-up.

![High-Priority Lead Notification](https://github.com/n8n-tin/ai-customer-support-agent/blob/main/screenshots/lead-notification.png)


---
## 🧪 Testing

The workflow was tested against multiple business scenarios, including:

| Scenario                      | Result              |
| ----------------------------- | ------------------- |
| Standard customer inquiry     | ✅ PASS              |
| High-intent customer          | ✅ PASS              |
| Unknown question              | ✅ PASS              |
| Unknown + high-intent inquiry | ✅ PASS              |
| Low-intent inquiry            | ✅ PASS              |
| Error handling                | ⚠️ Partially tested |


Detailed testing documentation is available in:

docs/testing.md

---
## 🛠️ Technology Stack

| Component           | Technology    |
| ------------------- | ------------- |
| Automation Platform | n8n           |
| Hosting             | Render        |
| AI Model            | Google Gemini |
| Knowledge Base      | Google Docs   |
| CRM                 | Google Sheets |
| Notifications       | Gmail         |
| Documentation       | GitHub        |

---

## 📊 Business Value

This automation demonstrates how AI and workflow automation can help businesses:

Reduce repetitive customer support work
Improve response consistency
Identify high-value leads automatically
Reduce manual lead qualification
Escalate complex inquiries to humans
Centralize customer information
Improve visibility into workflow failures

The goal is not to replace human support, but to automate repetitive work and help teams focus their time on higher-value interactions.

---
## 🔮 Future Improvements

Potential next steps include:

Replace Manual Trigger with a production Webhook
Connect the CRM to HubSpot or another CRM platform
Add customer conversation history
Add automated follow-up emails
Add lead-status tracking
Add analytics and reporting
Add authentication and production security
Add monitoring and alerting
Add additional communication channels such as WhatsApp

---
## 📁 Project Structure

```
ai-customer-support-agent/
│
├── docs/
│   ├── README.md
│   └── testing.md
│
├── screenshots/
│
└── README.md
```
---
## 👩‍💻 Project Purpose

This project was created as a practical demonstration of AI workflow automation, business process automation, structured AI outputs, conditional logic, human-in-the-loop escalation, and CRM integration.

It demonstrates how business requirements can be translated into an automated workflow using n8n and AI.

---
## 📌 Key Skills Demonstrated

AI Workflow Automation
n8n
Google Gemini
Prompt Engineering
Structured AI Output
Business Process Automation
Lead Qualification
Lead Scoring
Conditional Logic
Human-in-the-Loop Automation
CRM Integration
Error Handling
Workflow Testing
Process Mapping

---


