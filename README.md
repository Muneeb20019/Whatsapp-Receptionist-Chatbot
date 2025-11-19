# AI-Powered WhatsApp Receptionist

An automated receptionist built with n8n that handles customer inquiries via WhatsApp/SMS, gathers booking details using an AI agent, and saves finalized appointments directly into Airtable.

---

## Key Features

-   **Receives incoming customer messages via Twilio,** acting as the first point of contact.
-   **Automated Data Extraction:** Intelligently extracts key booking information (name, phone, pest type, address, etc.) from the conversation.
-   **Stateful Memory:** Remembers the conversation history for each customer, which is logged in Google Sheets.
-   **Data Persistence:** Saves finalized lead and booking data directly into Airtable.

---

## How It Works (Workflow Breakdown)

[
](https://github.com/Muneeb20019/Whatsapp-Receptionist-Chatbot/blob/main/AI-Powered%20WhatsApp%20Receptionist.png?raw=true)

This workflow is triggered by an incoming message from a service like Twilio.

1.  **Trigger & Memory Retrieval:** A **Twilio Trigger** receives a new message. The workflow then retrieves the past conversation history for that customer from a Google Sheet.
2.  **AI Agent Interaction:** The new message and the conversation history are passed to an **AI Agent** (powered by an OpenAI Model). The agent follows a detailed system prompt to either gather more information or confirm a booking.
3.  **Data Processing:** A **Code Node** parses the AI's output. It separates the conversational reply from the structured booking data.
4.  **Conversation Logging:** The transcript of the conversation between the company and the customer is saved in Google Sheets for record-keeping.
5.  **Finalization:** When a deal is closed, all of the captured lead data is saved as a new, structured record inside Airtable.

---

## Technology Stack

-   **Automation Platform:** [n8n.io](https://n8n.io/)
-   **AI Model:** OpenAI (GPT-4o)
-   **SMS/WhatsApp Gateway:** Twilio
-   **Primary Data Storage:** Airtable
-   **Conversation Logging:** Google Sheets
-   **Custom Logic:** JavaScript (in Code Nodes)

---

## Solving a Key Business Challenge

This project solves a critical business challenge for a pest control company by replacing their manual, time-consuming lead intake process with an intelligent 24/7 AI receptionist. Previously, staff spent valuable time answering calls and emails, asking repetitive questions just to qualify a lead or provide a quote, and risked losing business after hours. This automated workflow instantly engages customers via WhatsApp or SMS, automatically qualifies them by gathering all necessary details, provides immediate price quotes, and seamlessly saves confirmed bookings directly into Airtable. This transforms their operation by eliminating manual data entry, capturing every potential lead, and freeing up the specialists to focus on delivering their pest control services rather than administrative tasks.

## ✍️ Author

* **Muneeb Ali Khan** - https://github.com/Muneeb20019  -   https://www.linkedin.com/in/muneeb-ali-khan-2a1675365
