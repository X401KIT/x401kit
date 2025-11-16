# 🚀 Telegram Bot Setup for X401

![Telegram](https://img.shields.io/badge/telegram-bot-blue?logo=telegram) ![Python](https://img.shields.io/badge/python-3.11-blue)

This guide walks you through creating a Telegram bot, adding it to a group, promoting it to admin, sending a test message, and fetching essential IDs for **X401** usage. By the end, you'll have your **Bot Token** and **Group/Channel ID** ready to use.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Step 1: Create a Telegram Bot](#step-1-create-a-telegram-bot)
- [Step 2: Add the Bot to a Telegram Group](#step-2-add-the-bot-to-a-telegram-group)
- [Step 3: Promote the Bot to Admin](#step-3-promote-the-bot-to-admin)
- [Step 4: Send a Test Message](#step-4-send-a-test-message)
- [Step 5: Fetch Group/Channel ID Using Raw API](#step-5-fetch-groupchannel-id-using-raw-api)
- [Workflow Diagram](#workflow-diagram)
- [Important Notes](#important-notes)
- [Troubleshooting](#troubleshooting)

---

## 🎯 Overview

By following this guide, you will obtain:
- ✅ **Bot Token** (from BotFather)
- ✅ **Group/Channel ID** (from Telegram API)

These credentials are essential for integrating your bot with **X401**.

---

## Step 1: Create a Telegram Bot

Telegram's **BotFather** is the central hub for creating and managing all Telegram bots.

1. Open Telegram and search for **[@BotFather](https://t.me/BotFather)**
2. Start a chat and run the command:

```text
/newbot
```

3. Enter a **display name** for your bot (e.g., "X401 Notifier")
4. Choose a **username** (must end with `bot`, e.g., `my_x401_bot`)
5. BotFather will provide your **Bot Token**:

```text
123456789:ABCdefGHIjklMNOpqrSTUvwxYZ
```

6. **Save this token securely** — this is your Bot ID/Token

> ⚠️ **Important**: Never share your bot token publicly. Anyone with this token can control your bot.

---

## Step 2: Add the Bot to a Telegram Group

1. Open the **Telegram group** where you want the bot to operate
2. Click on the group name to open **Group Info**
3. Select **Add Members**
4. Search for your bot by username (e.g., `@my_x401_bot`)
5. Add the bot to the group
6. Ensure at least **one message is sent** in the group after adding the bot (this is required for the bot to detect the chat via `/getUpdates`)

---

## Step 3: Promote the Bot to Admin

Bots require **admin privileges** to perform certain actions, like invite link generation.

1. Open **Group Info** → **Administrators**
2. Click **Add Administrator**
3. Select your bot from the member list
4. Enable the following permissions:
   - ✅ **Invite Users via Link** (required)
   - ✅ **Manage Chat** (optional, for additional features)
5. Click **Done** to save

---

## Step 4: Send a Test Message

Send any message in the group to trigger an update. For example:

```text
/start
```

or simply:

```text
Hello bot!
```

This ensures the bot receives a message so that the **Group ID** can be fetched via the Telegram API.

---

## Step 5: Fetch Group/Channel ID Using Raw API

Now you'll use the Telegram Bot API to retrieve your Group/Channel ID.

### Method 1: Using Your Browser

1. Replace `<BOT_TOKEN>` with your actual bot token in the URL below:

```
https://api.telegram.org/bot<BOT_TOKEN>/getUpdates
```

2. Open this URL in your browser
3. You'll see a JSON response like this:

```json
{
  "ok": true,
  "result": [
    {
      "update_id": 438410385,
      "message": {
        "message_id": 123,
        "from": {
          "id": 987654321,
          "first_name": "John"
        },
        "chat": {
          "id": -1001234567890,
          "title": "My X401 Group",
          "type": "supergroup"
        },
        "date": 1699876543,
        "text": "/start"
      }
    }
  ]
}
```

4. Look for the `"chat"` object and find the `"id"` field:

```json
"chat": {
  "id": -1001234567890,
  "title": "My X401 Group",
  "type": "supergroup"
}
```

5. The value of `"id"` (e.g., `-1001234567890`) is your **Group/Channel ID**

### Method 2: Using curl (Command Line)

```bash
curl https://api.telegram.org/bot<BOT_TOKEN>/getUpdates
```

### Method 3: Using Python

```python
import requests

BOT_TOKEN = "your_bot_token_here"
url = f"https://api.telegram.org/bot{BOT_TOKEN}/getUpdates"

response = requests.get(url)
data = response.json()

for update in data.get("result", []):
    chat = update.get("message", {}).get("chat", {})
    print(f"Chat ID: {chat.get('id')}")
    print(f"Chat Title: {chat.get('title')}")
    print(f"Chat Type: {chat.get('type')}")
```

---

## 📊 Workflow Diagram

```
┌─────────────────┐
│   1. BotFather  │
│  Create New Bot │
└────────┬────────┘
         │
         ▼
    Bot Token
         │
         ▼
┌─────────────────┐
│  2. Add Bot to  │
│  Telegram Group │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ 3. Promote Bot  │
│   to Admin      │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ 4. Send Test    │
│    Message      │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ 5. Call API     │
│  /getUpdates    │
└────────┬────────┘
         │
         ▼
   Group/Channel ID
         │
         ▼
┌─────────────────┐
│  ✅ Ready for   │
│     X401!       │
└─────────────────┘
```

---

## 📝 Important Notes

- ✅ **Bot must be in the group** and **must be an admin** for full functionality
- ✅ `/getUpdates` only returns **unread updates**, so sending a new message after adding the bot is necessary
- ✅ **No programming required** — the raw API provides the IDs directly
- ✅ Group IDs typically start with `-` (negative numbers)
- ✅ Supergroup IDs typically start with `-100`
- ⚠️ **Never commit your bot token** to version control (use environment variables)

---

## 🔧 Troubleshooting

### Problem: `/getUpdates` returns empty result

**Solution**: Make sure you've sent at least one message in the group **after** adding the bot.

### Problem: Bot not receiving messages

**Solutions**:
- Ensure the bot is actually added to the group
- Check that privacy mode is disabled (use `/setprivacy` with BotFather)
- Verify the bot hasn't been kicked or removed

### Problem: Can't find the Group ID

**Solution**: Look for the `chat.id` field in the JSON response. It should be a negative number for groups.

### Problem: Bot can't perform admin actions

**Solution**: Verify the bot has been promoted to admin with the necessary permissions.

---

## 🎉 You're Done!

You now have:
- ✅ **Bot Token** → from BotFather
- ✅ **Group/Channel ID** → from `/getUpdates`

These are all the credentials required for **X401** usage. You can now integrate your Telegram bot with your application!

---

## 📚 Additional Resources

- [Telegram Bot API Documentation](https://core.telegram.org/bots/api)
- [BotFather Commands Reference](https://core.telegram.org/bots#6-botfather)
- [Telegram Bot API - getUpdates](https://core.telegram.org/bots/api#getupdates)

---

**Made with ❤️ for X401**