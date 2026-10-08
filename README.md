# AI Operations X-Ray Lead Magnet

An enterprise-grade, multi-step lead magnet that captures company domains, analyzes operational intake data using web scraping and LLMs, generates 3 ranked automation roadmaps, and conditionally provides website conversion audits.

![Architecture Flow](https://img.shields.io/badge/Architecture-Cloudflare%20%7C%20n8n%20%7C%20OpenAI%20%7C%20Airtable-black)

---

## 🚀 Architecture Overview

* **Frontend:** HTML5 / CSS3 (Moore IQ UX Pattern) hosted on **Cloudflare Pages**.
* **Orchestration:** **n8n** Webhook Pipeline with conditional branching.
* **Scraping:** **Apify / Web Scraper** for domain text extraction.
* **AI Analysis:** **OpenAI GPT-4o-mini** structured JSON extraction.
* **CRM Storage:** **Airtable** for lead capture and operational logs.
* **Email Delivery:** **Resend API** for formatted executive briefings.

---

## 📋 System Workflow

1. **Intake Funnel (`index.html`):**
   * Step 1: Company Domain & optional "Free Website Audit" toggle.
   * Step 2: Team Size, Operational Time Drain, and Cost Impact.
   * Step 3: Contact Details (Name & Business Email).
2. **Backend Processing (n8n):**
   * Ingests form payload via POST webhook.
   * Scrapes domain content.
   * Evaluates conditional logic (`include_website_audit`).
   * Calls **LLM 1** to generate 3 ranked high-leverage AI automation opportunities.
   * Calls **LLM 2** (if toggled) to identify 3 website CRO bottlenecks.
   * Normalizes output via JavaScript Code Node.
   * Upserts record into **Airtable** CRM.
   * Dispatches tailored executive report via **Resend**.