# n8n-BFL-hackathon
06September2025, Creative AI hackathon submission repo


# AI-Powered Travel Newsletter Automation

This repository contains an n8n template that automates the generation of a travel newsletter using AI, from idea sourcing to visual storytelling.

---

### 🚀 Project Overview

This project demonstrates how to connect an **n8n** automation workflow with services like **OpenAI** and **Airtable** to create a fully automated content pipeline for a travel newsletter.

**What it does:**
* Scans Google Trends (in Germany & France) and other news sources for potential travel ideas.
* Passes the data to an **OpenAI** model to generate a title, summary, and recommendation for each destination.
* Saves the generated content to an **Airtable** base for tracking.
* Sends a summary email via **Outlook** for human review and selection (Human-in-the-Loop).
* Triggers **Flux Kontext** to generate a visual story once a destination is approved.
* Saves the final images back to a separate table in Airtable.

---

### 🛠️ Setup Instructions

#### Requirements

You will need accounts and API keys for the following services to use this template.

* **n8n** (a self-hosted instance or an n8n cloud account).
* **Airtable Account**: You will need an API key and a Base ID. You can get your API key from your [Airtable account settings](https://airtable.com/account).
* **OpenAI API Key**: You can get an API key from the [OpenAI Platform](https://platform.openai.com/api-keys).
* **Outlook Account** (or Gmail) for the human-in-the-loop approval step.
* **Access to Flux Kontext** for the final image generation step.

#### Steps

1.  **Set up Airtable**
    * Create a new Airtable Base for this project.
    * Create two tables inside it: a table for `Generated Content` and another for `Generated Images`.
    * In the `Generated Content` table, create fields for `Title`, `Summary`, `Recommendation`, and `Status` (a single-select field with options like "Pending" and "Selected").

3.  **Import the Workflow into n8n**
    * Open your n8n canvas.
    * Select "Import from File" and choose the `BFL_hackathon_Jeongwoo.json` file from this repository.

4.  **Configure n8n Credentials**
    * In your n8n instance, go to the "Credentials" section from the sidebar.
    * Add new credentials for **Airtable** and **OpenAI** using the API keys you obtained in the requirements step.

5.  **Update the Workflow Nodes**
    * Open the imported workflow on your canvas.
    * Double-click on each **Airtable node** and configure it: select your credentials, and input the correct Base ID and Table Name.
    * Select your credentials for the **OpenAI node**.
    * Update the **Outlook (or Email) node** with your email address for receiving review notifications.

6.  **Activate the Workflow**
    * Click the "Save" button and then toggle the workflow to "Active". Your automated newsletter agent is now ready!