# 👤 New Hire IT Onboarding Workflow

> **Automated IT setup requests using n8n, Airtable, and dynamic approval emails**

---

## 📌 Overview

This workflow simplifies and standardizes IT onboarding by collecting new hire information via a form and automating downstream setup steps. It stores onboarding requests in Airtable, generates a branded email for the IT team, includes an approval link, and updates records upon confirmation—freeing HR and IT teams from manual handoffs and email chains.

---

## 💡 The Problem

Coordinating equipment requests, software provisioning, and systems access for new employees was an inefficient, error-prone process. It required back-and-forth emails between HR and IT, and critical details were often missing or delayed.

---

## ⚙️ The Workflow

1. **📝 Form Trigger (n8n Form node)**  
   A custom form collects all required setup info:
   - New hire name & email
   - Manager details
   - Hardware (computer, monitors, peripherals)
   - Software & systems access
   - Business line assignment

2. **📋 Airtable Record Creation**  
   Data is mapped into an Airtable table for internal tracking and auditing.

3. **📧 Email to IT Team**  
   A rich HTML email is sent to IT with a breakdown of hardware/software needs and an embedded **approval link**.

4. **✅ Approval Webhook**  
   When IT clicks the approval link, n8n listens via webhook and updates the Airtable record's status to `Completed`.

5. **📨 Completion Notification**  
   A final confirmation email is sent to HR or the hiring manager.

---

## 🔧 Tech Stack

- [n8n](https://n8n.io) – Orchestration and form trigger
- Airtable – Record management and status tracking
- Gmail – Email notifications
- Webhooks – Click-to-approve flow for IT

---

## 🖼️ Sample Email Output

```text
Subject: New Employee - HR

New Hire IT Setup Request – drew@example.com

Please prepare the necessary equipment and system access for a new hire joining the Hazard Quest business line.

Name: Drew Reutlinger  
Manager: Jenna Porter  
Computer: Mac Laptop  
Monitor: Two  
Peripherals: Webcam, Headset  
Software: Adobe Creative Suite, Docker  
System Access: Salesforce, DevOps  

[Click here to approve setup]
