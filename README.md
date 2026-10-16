# Portfolio Project 01: Automated Lead Ingestion & Notification Pipeline

## Overview
An automated backend workflow built in n8n designed to capture inbound leads from website contact forms, perform data validation, log structured entries into Google Sheets in real-time, and dispatch instant email alerts via Gmail.

## Architecture & Flow
1. **Webhook Node (Trigger):** Listens for incoming POST requests containing lead payloads (`name`, `phone`, `message`).
2. **If Node (Validation):** Evaluates incoming payloads to ensure mandatory fields are populated, dropping empty or test submissions.
3. **Google Sheets Node (Storage):** Automatically appends validated lead records along with a generated timestamp (`{{ $now }}`) into a centralized tracking sheet.
4. **Gmail Node (Notification):** Formats and dispatches a structured multi-line summary straight to the operations team inbox.

## Tech Stack
* **Orchestration:** n8n Cloud
* **Data Storage:** Google Sheets
* **Notifications:** Gmail API
* **Data Format:** JSON / REST Webhooks

## Business Value
Eliminates manual lead logging, prevents data entry errors, and ensures sub-minute response times for inbound business inquiries.
