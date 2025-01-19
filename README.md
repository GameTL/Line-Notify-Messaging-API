# 🚀 Line Notify Messaging API Quick Start

A brief guide to using the Messaging API as a replacement for the soon-to-be-deprecated Line Notify service.

---

## 📜 Scope

Line Notify, which allowed sending notifications using tokens, is set to be discontinued in **mid-2025**. This document outlines how to achieve similar functionality using the **Line Messaging API** and webhooks, focusing on sending POST requests with a bearer token to deliver messages. 

### 📌 Use Case:
This guide is tailored for:
- Sending **alerts** from dashboards (e.g., Grafana) to **group chats**.
- Replicating functionality for scenarios like **user notifications** or **system alerts**.

---

## 🧭 Workflow Overview

1. **Create Accounts**: 
   - Set up a [Line Official Account](https://developers.line.biz/console/) and enable the Messaging API.
2. **Join Group Chat**:
   - Add the bot to your group chat for group-specific messaging functionality.
3. **Use a Webhook Tester**:
   - Capture group-specific data, like the **Group ID**, by testing webhook payloads.

---

## 📋 What’s Covered

This guide will walk you through:
- Setting up the **Line Official Account** and enabling the **Messaging API**.
- Capturing the **Group ID** needed to send messages to group chats.
- Configuring webhooks and using webhook testing tools to debug and retrieve user data.

---

## ⚙️ Setting Up

1. **Create a Line Official Account**:
   - Visit [Line Developers Console](https://developers.line.biz/console/).
   - Register your account and create a new channel with **Messaging API** enabled.

2. **Obtain Channel Access Token**:
   - Navigate to your channel settings.
   - Generate and save the **Channel Access Token** (bearer token).

3. **Configure Webhook**:
   - Use a webhook testing tool (e.g., [Webhook.site](https://webhook.site)) to capture events.
   - Add the webhook URL in your channel’s **Webhook Settings**.

---

## 📧 Sending Messages to Group Chats

1. **Add the Bot to Your Group Chat**:
   - Invite your bot to the group chat.
   - Ensure the bot has permission to access group data.

2. **Retrieve Group ID**:
   - Use the webhook tester to capture events triggered in the group chat (e.g., when someone sends a message).
   - Extract the **Group ID** from the payload.

3. **Send POST Requests**:
   - Use the **Push Message API** endpoint:
     ```http
     POST https://api.line.me/v2/bot/message/push
     ```
   - Include the bearer token and group-specific payload:
     ```json
     {
       "to": "GROUP_ID",
       "messages": [
         {
           "type": "text",
           "text": "Your alert message here!"
         }
       ]
     }
     ```

---

## 🛠️ Tools and Resources

- **Webhook Testing**: [Webhook.site](https://webhook.site)
- **Line Developers Console**: [Line Biz Developers](https://developers.line.biz/console/)
- **Messaging API Documentation**: [Line Messaging API Docs](https://developers.line.biz/en/docs/messaging-api/)

---

## 💬 Feedback

Feel free to leave feedback or suggestions in the **Issues** section of this repository. Contributions are always welcome!

---
