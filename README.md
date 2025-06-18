## Smart\_Scheduler\_AiAgent

An AI-driven assistant built on n8n for managing emails, calendars, and more through text and voice interaction via Telegram and Eleven Labs.

---

## 🚀 Features

* **Unified Communication:** Manage email, calendar, and tasks through text or voice in Telegram.
* **AI Tool Integration:** Invoke other AI agents and services for complex tasks like summarization.
* **Email Automation:** Send emails and receive the latest messages as text or audio via Eleven Labs.
* **Calendar Scheduling:** Create meetings with generated links and automated attendee invites.
* **Contact Management:** Read/write Google Sheets to maintain frequent contacts and logging.
* **Adaptive Prompt Handling:** Robust conversation management for ambiguous or uneven queries.
* **Standardized Email Formatting:** Consistent templates for automated outbound emails.

---

## 🔧 Prerequisites

* **n8n (v1.x or later)** installed locally or on a server
* **Telegram Bot** and **Bot Token**
* **Google Cloud Credentials** (Sheets & Calendar API enabled)
* **Gmail API Credentials**
* **OpenAI/Gemini API Key**
* **Eleven Labs API Key** (optional: configure after obtaining paid credentials)

---

## ⚙️ Setup & Configuration

1. **Clone the repository**

   ```bash
   git clone https://github.com/your-username/Smart_Scheduler_AiAgent.git
   cd Smart_Scheduler_AiAgent
   ```\

4. **Import Workflow**

   * Open your n8n instance
   * Go to **Workflows > Import**
   * Upload `Smart_Scheduler_AiAgent.json`

5. **Install & Activate Nodes**

   * Ensure **Telegram**, **HTTP Request**, **Google Sheets**, **Google Calendar**, and **Gmail** nodes are enabled in `Settings > Nodes`.

6. **Connect & Test**

   * Start the workflow
   * Send a test message to your Telegram bot
   * Verify operations: email fetch, calendar creation, sheet update

---

## 🧩 Design Choices

1. **n8n as Orchestration Layer**

   * **Why?** No-code flow management speeds development and simplifies maintenance.
   * **How?** Each task (email fetch, sheet update) is encapsulated in dedicated nodes.

2. **Telegram for UI**

   * **Why?** Familiar chat interface, cross-platform, and supports both text & voice.
   * **How?** Telegram node handles incoming updates; messages are parsed to determine the operation.

3. **Google Services Integration**

   * **Why?** Ubiquitous and reliable APIs for email, calendar, and sheets.
   * **How?** OAuth-based credentials stored securely; nodes perform CRUD operations.

4. **Eleven Labs for Voice Output**

   * **Why?** High-quality TTS for improved accessibility and hands-free interaction.
   * **How?** HTTP Request node sends text to Eleven Labs and returns an audio file link.

5. **Environment-Based Config**

   * **Why?** Secure secret management and portability across environments.
   * **How?** `.env` file reads variables via n8n’s Credentials feature.

---

## 🏃‍♀️ Usage Examples

1. **Fetch Latest Emails**

   * **Command:** `latest emails`
   * **Result:** Bot replies with a summary text or voice note of the 5 most recent emails.

2. **Schedule Meeting**

   * **Command:** `schedule meeting with John tomorrow at 3pm`
   * **Result:** Creates a calendar event, generates a link, sends invites via email.

3. **Add & Update Contact**

   * **Command:** `add contact Jane Doe jane@example.com`
   * **Result:** Appends to Google Sheet; confirms with a Telegram message.

---

## 📜 License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---
