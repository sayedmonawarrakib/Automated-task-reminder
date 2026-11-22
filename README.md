# 🤖 Telegram Notification Bot using n8n

An automated Telegram notification system built with **n8n** and the **Telegram Bot API**. This project sends instant Telegram notifications whenever a website, registration form, order system, or customer inquiry submits new information through a webhook.

## 📌 Project Overview

The Telegram Notification Bot automates the process of receiving and delivering notifications. It uses an n8n Webhook to receive incoming data and a Telegram Bot to send formatted messages directly to an administrator's Telegram account.

The main goal of this project is to understand workflow automation, webhook integration, API connections, and real-time notifications using n8n.

## 🖼️ Screenshot of the Project:

<img width="987" height="590" alt="Screenshot 2026-11-22 122609" src="https://github.com/user-attachments/assets/2e7ce4a1-e402-4468-9ff9-80d13a46d9c2" />
Automation workflow ⬆️
<img width="559" height="267" alt="Screenshot 2026-11-22 123509" src="https://github.com/user-attachments/assets/8761e706-3dfd-438c-8ca3-c4cf54cb99b0" />
Google Sheet ⬆️
<img width="824" height="899" alt="Screenshot 2026-11-22 140259" src="https://github.com/user-attachments/assets/a60e9d2c-a730-4d8d-ac13-e87443480421" />
Telegram Message ⬆️


## ⚙️ Workflow Architecture

```text
Website / Registration Form / Order System
                  |
                  v
             Webhook Node
                  |
                  v
            n8n Workflow
                  |
                  v
             Telegram Node
                  |
                  v
          Telegram Notification
                  |
                  v
           Administrator
```

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| n8n | Workflow automation |
| Telegram Bot API | Sending notifications |
| BotFather | Creating Telegram bots |
| Webhook | Receiving incoming data |
| JSON | Data exchange |
| HTTP POST | Sending webhook requests |

## ✨ Features

- Real-time Telegram notifications.
- Webhook-based data collection.
- Automated message delivery.
- Custom notification messages.
- Customer registration notifications.
- New order notifications.
- Customer inquiry notifications.
- No manual notification required.

## 📂 Project Structure

```text
telegram-notification-bot/
│
├── README.md
│
├── workflow/
│   └── telegram-notification-workflow.json
│
└── screenshots/
    ├── workflow.png
    ├── webhook-node.png
    └── telegram-notification.png
```

## 🚀 Installation and Setup

### Step 1: Create a Telegram Bot

1. Open Telegram.
2. Search for [@BotFather](https://t.me/BotFather).
3. Send `/newbot`.
4. Enter your bot name and username.
5. Copy the generated API token and keep it private.

### Step 2: Get Your Telegram Chat ID

1. Open your newly created bot.
2. Click Start or send `/start`.
3. Send a test message.
4. Use the Telegram Bot API `getUpdates` method to retrieve your personal Chat ID.

API endpoint:

```text
https://api.telegram.org/bot<YOUR_BOT_TOKEN>/getUpdates
```

### Step 3: Create an n8n Workflow

1. Open your n8n dashboard.
2. Create a new workflow.
3. Add a Webhook node.
4. Set HTTP Method to `POST`.
5. Configure a webhook path.

### Step 4: Configure Telegram

1. Add a Telegram node.
2. Select the Send Message operation.
3. Create Telegram credentials using your BotFather API token.
4. Enter your personal Chat ID.
5. Configure your notification message.

### Step 5: Connect the Nodes

Connect the Webhook node to the Telegram node.

```text
Webhook → Telegram
```

### Step 6: Test the Workflow

Send a POST request to your Webhook URL with sample JSON data:

```json
{
  "name": "Rakib",
  "event": "New Customer Registration",
  "email": "rakib@example.com",
  "phone": "01712345678"
}
```

If configured correctly, your Telegram bot will send a notification to your Telegram account.

## 📩 Sample Notification

```text
🔔 NEW NOTIFICATION RECEIVED

Hello Admin!

A new event has been received.

📋 Notification Details

👤 Name: Rakib
📧 Email: rakib@example.com
📱 Phone: 01712345678
📌 Event: New Customer Registration

⚙️ System Information

Platform: n8n Automation
Status: Successfully Received
Source: Website Webhook

🤖 Automated Notification System
```

## 🔐 Security

- Never upload your Telegram Bot API token to GitHub.
- Never publish private credentials or API keys.
- Use n8n credentials to store sensitive information.
- Use environment variables where appropriate.
- Keep private webhook URLs and production credentials secure.

## 🎯 Learning Outcomes

Through this project, I practised:

- Understanding workflow automation.
- Creating and configuring webhooks.
- Integrating third-party APIs.
- Working with Telegram Bot API.
- Handling JSON data.
- Building automated notification systems.
- Troubleshooting API authentication and permission errors.

## 🔮 Future Improvements

- Add Google Sheets integration.
- Support multiple notification types.
- Add email notifications.
- Integrate with an e-commerce website.
- Add customer inquiry tracking.
- Add conditional notification logic using the n8n IF node.

## 👨‍💻 Author

**Sayed Monawar Rakib**

Computer Science & Technology | Automation Enthusiast

GitHub: www.https://github.com/sayedmonawarrakib

## 📄 License

This project is open-source and available under the MIT License.
