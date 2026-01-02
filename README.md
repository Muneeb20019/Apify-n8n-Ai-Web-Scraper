# 🤖 AI-Powered Automated Web Scraper & Lead Gen System

## 🌟 Project Overview
This project features a robust automation pipeline built using **n8n** to automate web scraping and lead enrichment. The system orchestrates multiple services to extract raw data from websites, process it using **GPT-4o**, and deliver high-quality, structured leads directly into **Google Sheets**.

### 🛠️ What it does:
- **Orchestrates** complex workflows between different APIs using n8n.
- **Automates** data collection using Apify actors within the workflow.
- **Enriches** and categorizes company information using AI logic.
- **Updates** a master database in real-time, preventing manual data entry errors.

---

## 🏗️ The Workflow Architecture (n8n)
The pipeline is designed using n8n's visual node-based editor for seamless data flow and reliability.

![Workflow Architecture](./images/workflow.png)

### ⚙️ Pipeline Steps:
1.  **Schedule Trigger ⏰:** A cron-job node that initiates the workflow at specific intervals.
2.  **Apify Actor Node 🎭:** n8n triggers an Apify scraper to crawl target websites.
3.  **Wait & Fetch 📥:** The workflow pauses for completion and then pulls the raw dataset.
4.  **AI Agent (OpenAI) 🧠:** 
    *   n8n sends the raw data to an OpenAI node (GPT-4o).
    *   The AI extracts key contact persons, emails, and phone numbers.
    *   It analyzes company descriptions to assign industry categories.
5.  **Google Sheets Integration 📊:** The final node appends or updates the processed leads into a structured sheet.

---

## 📊 Final Output (The Results)
The result is a production-ready dataset with validated business profiles and categorized industry data.

![Google Sheets Output](./images/results.png)

### 📋 Key Data Points Captured:
*   🏢 **Company & Website Details**
*   📍 **Address & Event Booth Location**
*   🔗 **Social Media Links** (LinkedIn, Facebook)
*   🏷️ **AI-Classified Industry Segments**
*   👤 **Decision Maker Contacts** (Name, Email, Role, Phone)

---

## 🧪 Tech Stack
- **Workflow Orchestrator:** [n8n](https://n8n.io/)
- **Scraping Engine:** Apify
- **AI Model:** OpenAI GPT-4o
- **Database:** Google Sheets
- **Logic:** JavaScript / JSON / Node-based Automation

---

## 💡 Key Use Cases
- **Automated Sales Prospecting:** Building verified lead lists on autopilot.
- **Event Exhibitor Tracking:** Monitoring trade show participants.
- **Market Intelligence:** Analyzing and categorizing competitors at scale.

---

## ✍️ Author
**Muneeb Ali Khan**  
*   🚀 [GitHub Profile](https://github.com/Muneeb20019)
*   💼 [LinkedIn Profile](https://www.linkedin.com/in/muneeb-ali-khan-2a1675365)
