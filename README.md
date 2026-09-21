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
<img width="562" height="836" alt="image" src="https://github.com/user-attachments/assets/46a8dcdb-dc67-408e-827c-2f2cf4c66ffe" />

2. Telegram message
<img width="832" height="665" alt="image" src="https://github.com/user-attachments/assets/e29f8051-dafc-482c-8abd-9f35374ad00f" />

3. Created record in the Google Sheet
<img width="993" height="207" alt="image" src="https://github.com/user-attachments/assets/c65d306d-b9c2-45f8-965c-19475bfd10f0" />
