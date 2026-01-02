# 🤖 AI-Powered Automated Web Scraper & Lead Gen System

![n8n](https://img.shields.io/badge/Workflow-n8n-FF6C37?style=flat&logo=n8n&logoColor=white)
![Apify](https://img.shields.io/badge/Scraping-Apify-97ca00?style=flat&logo=apify&logoColor=white)
![OpenAI](https://img.shields.io/badge/AI-GPT--4o-412991?style=flat&logo=openai&logoColor=white)
![Google Sheets](https://img.shields.io/badge/Storage-Google%20Sheets-34A853?style=flat&logo=google-sheets&logoColor=white)

## 🌟 Project Overview
This project demonstrates a fully autonomous **Data Extraction and Enrichment Pipeline**. Built using **n8n** as the central orchestrator, it leverages **Apify's** powerful scraping capabilities to bypass bot detection and **OpenAI's GPT-4o** to transform unstructured web data into high-value, categorized leads.

Unlike traditional scrapers that produce "noisy" data, this pipeline uses an **AI Agent** to act as a digital researcher—verifying contact details and categorizing companies based on their product offerings before saving them.

---

## 🏗️ Technical Architecture & Workflow
The system follows a linear logic designed for reliability and data integrity.

![n8n Workflow Architecture](https://github.com/Muneeb20019/Apify-n8n-Ai-Web-Scraper/blob/main/n8n%20apify.jpg?raw=true)

### 🔍 Deep Dive into the Nodes:

1.  **Schedule Trigger (Cron) ⏰:** 
    *   Automates the start of the workflow (e.g., daily at 9 AM). This ensures the lead list is always fresh without manual intervention.
2.  **Apify Actor (Run an Actor) 🎭:** 
    *   Triggers a specialized scraping "Actor." This node is configured to target specific directories or websites. Apify is used here because of its superior proxy management and browser fingerprinting evasion.
3.  **Wait Node ⏳:** 
    *   **Crucial Logic:** Scraping is an asynchronous task. This node ensures n8n waits for the Apify Actor to finish its job before attempting to pull the data, preventing "empty data" errors.
4.  **Get Dataset Items 📥:** 
    *   Once the scraper is finished, this node pulls the raw JSON data. This usually includes raw HTML snippets, text, and metadata.
5.  **AI Agent (Powered by OpenAI) 🧠:** 
    *   The "Brain" of the operation. It receives the raw text and performs:
        *   **Entity Extraction:** Finding names, emails, and phone numbers.
        *   **Classification:** Analyzing the company description to assign it to industry categories (e.g., Aerospace, Manufacturing).
        *   **Standardization:** Cleaning up address formats and website URLs.
6.  **Google Sheets (Append or Update) 📊:** 
    *   The final storage layer. It uses **UPSERT logic**—if the company already exists in the sheet, it updates the record; if it's new, it appends a new row.

---

## 📊 Business Intelligence Output
The final result is a structured, "sales-ready" spreadsheet. Each row represents a verified lead with deep context.

![Processed Data Output](https://github.com/Muneeb20019/Apify-n8n-Ai-Web-Scraper/blob/main/website%20scrapper.png?raw=true)

### 📋 Data Enrichment Details:
*   🏢 **Company Profile:** Name, Website, and Social Media links (LinkedIn/Facebook).
*   📍 **Logistics Data:** Physical address, Country, and Booth/Location (useful for trade show tracking).
*   🏷️ **AI Categorization:** Automatically assigns "Product Categories" based on website content analysis.
*   👤 **Verified Contacts:** Finds the specific contact person (e.g., CFO, Director) along with their verified email and phone number.

---

## 🧪 Detailed Tech Stack
*   **n8n:** Used for logic, API connections, and scheduling.
*   **Apify SDK:** Used for robust web crawling and data extraction.
*   **OpenAI GPT-4o API:** Used for Natural Language Processing (NLP) and data structuring.
*   **Google Sheets API:** Used as a low-cost, collaborative database for final output.
*   **JSON Processing:** Custom expressions used within n8n to map AI outputs to spreadsheet columns.

---

## 💡 Why This Project Matters
In a modern sales environment, manual lead generation is the biggest bottleneck. This project solves that by:
- **Scaling:** It can process thousands of records in the time it takes a human to process ten.
- **Accuracy:** The AI Agent filters out irrelevant data, ensuring only high-quality leads reach the sales team.
- **Automation:** It runs in the background, allowing teams to focus on closing deals rather than finding emails.

---

## ✍️ Author
**Muneeb Ali Khan**
*   🚀 [GitHub Profile](https://github.com/Muneeb20019)
*   💼 [LinkedIn Profile](https://www.linkedin.com/in/muneeb-ali-khan-2a1675365)
