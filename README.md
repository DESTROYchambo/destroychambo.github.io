# 🚀 Web Form for Automation Requests (n8n + Telegram)

![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)
![n8n](https://img.shields.io/badge/n8n-io-%23EA4B71.svg?style=for-the-badge&logo=n8n&logoColor=white)

A modern, responsive web form for collecting client requests for automation services. The project is implemented in a **Glassmorphism** style using neon animations. The form is designed for integration with **n8n** (via Webhook) and requires mandatory interaction with a **Telegram bot**.

[Page link](https://destroychambo.github.io/)

## Features

- **Modern UI/UX:** Dark Mode design with a frosted glass effect, gradients, and background animations.
- **Responsiveness:** Full support for mobile devices and desktops.
- **Telegram Logic:** Integrated reminder button about the need to send `/start` to the bot before submitting the form.
- **n8n Webhook:** Sending data (Full Name, Telegram ID, Urgency, Message) via a POST request.
- **UX Details:** Field validation, loading state, and a beautiful success message.

## 🛠 How it works (Workflow)

1.  **Entry:** The client opens the web page.
2.  **Bot Activation:** The client clicks on the animated Telegram button, goes to the bot, and presses `/start` (this is necessary for feedback).
3.  **Filling out:** The client enters their data:
    - First and Last Name.
    - Telegram ID (includes a link to a tool to get it).
    - Urgency level (Normal / Important / Urgent).
    - Description of the problem.
4.  **Submission:** The data is sent via `fetch` to the Webhook URL and recorded in a Google Sheet.
5.  **Success:** The client receives a visual confirmation.

## 📦 Data Structure (JSON)

The form sends the following object to the server:

```json
{
  "fullName": "Last Name First Name",
  "telegramId": "123456789",
  "urgency": "high",  // low | medium | high
  "message": "Text of the client's problem...",
  "timestamp": "2023-10-27T10:00:00.000Z"
}
```

## Screenshots
1. Filling in the data
<img width="521" height="827" alt="image" src="https://github.com/user-attachments/assets/b95194bb-1697-45f6-9a87-c0a4f7f5e02d" />

2. Telegram message
<img width="543" height="493" alt="image" src="https://github.com/user-attachments/assets/e9fc418d-2105-444a-96f2-ebea2f311569" />

3. Created record in the Google Sheet
<img width="848" height="97" alt="image" src="https://github.com/user-attachments/assets/39280207-2ec0-4afe-b46a-15b0b3a13d71" />

