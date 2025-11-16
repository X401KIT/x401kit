# 🎮 Discord Bot Setup for X401

![Discord](https://img.shields.io/badge/discord-bot-5865F2?logo=discord&logoColor=white) ![Status](https://img.shields.io/badge/status-ready-success)

This guide walks you through creating a Discord application, adding a bot user, generating an invite link, adding the bot to your server, and enabling Developer Mode to copy essential IDs for **X401** usage.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Part 1: Create Discord Application and Bot User](#part-1-create-discord-application-and-bot-user)
  - [Step 1: Create a New Application](#step-1-create-a-new-application)
  - [Step 2: Add a Bot User and Get the Token](#step-2-add-a-bot-user-and-get-the-token)
- [Part 2: Generate Invite Link and Add to Server](#part-2-generate-invite-link-and-add-to-server)
  - [Step 3: Generate the OAuth2 Invite Link](#step-3-generate-the-oauth2-invite-link)
  - [Step 4: Invite the Bot to Your Server](#step-4-invite-the-bot-to-your-server)
- [Part 3: Discord Client Setup (Developer Mode and IDs)](#part-3-discord-client-setup-developer-mode-and-ids)
  - [Step 5: Enable Developer Mode](#step-5-enable-developer-mode)
  - [Step 6: Copy Channel and Server IDs](#step-6-copy-channel-and-server-ids)
- [Workflow Diagram](#workflow-diagram)
- [Important Notes](#important-notes)
- [Troubleshooting](#troubleshooting)

---

## 🎯 Overview

By following this guide, you will obtain:
- ✅ **Bot Token** (from Discord Developer Portal)
- ✅ **Channel ID** (from Discord Client)

These credentials are essential for integrating your bot with **X401**.

---

## Part 1: Create Discord Application and Bot User

The Discord Developer Portal is the central hub for creating and managing all your Discord applications and bots.

### Step 1: Create a New Application

1. **Go to the Developer Portal:**
   - Navigate to [Discord Developer Portal](https://discord.com/developers/applications)
   - Log in with your Discord account

2. **Click "New Application":**
   - Located in the top right corner of the page

3. **Name the Application:**
   - Enter a name for your application (this will be the bot's display name)
   - Click **Create**
   - Accept the Terms of Service if prompted

> 💡 **Tip**: Choose a descriptive name that represents your bot's purpose (e.g., "X401 Notifier")

---

### Step 2: Add a Bot User and Get the Token

1. **Navigate to the Bot Tab:**
   - On the left sidebar, click the **Bot** tab

2. **Add the Bot:**
   - Click **Add Bot**
   - Confirm with **Yes, do it!**

3. **Get the Bot Token (Important):**
   - Under the **Token** section, click **Reset Token**
   - Copy the token immediately and **save it securely**
   
  

   > ⚠️ **CRITICAL**: Never share your bot token publicly. Anyone with this token can control your bot. Treat it like a password!



4. **Bot Permissions:**
   - Under **Bot Permissions**, you can set default permissions
   - Common permissions for X401:
     - ✅ **Send Messages**
     - ✅ **Read Message History**
     - ✅ **Create Instant Invite** (if needed)

5. **Save Changes** by clicking the **Save Changes** button at the bottom

---

## Part 2: Generate Invite Link and Add to Server

You must use the OAuth2 URL Generator to create a unique link that invites your bot with the correct permissions.

### Step 3: Generate the OAuth2 Invite Link

1. **Navigate to OAuth2:**
   - On the left sidebar, go to **OAuth2** → **URL Generator**

2. **Select Scopes:**
   - Check the `bot` checkbox
   - Optionally check `applications.commands` if using slash commands

3. **Select Bot Permissions:**
   - Based on your bot's needs, select appropriate permissions:
     - ✅ **create invite link**
     
   
   > ⚠️ **Warning**: Avoid selecting **Administrator** unless absolutely required. Grant only the minimum permissions needed.

4. **Copy the Generated URL:**
   - The invite URL at the bottom updates automatically as you select permissions
   - Copy this URL

   ```
   https://discord.com/api/oauth2/authorize?client_id=123456789012345678&permissions=2048&scope=bot
   ```

---

### Step 4: Invite the Bot to Your Server

1. **Open the Invite Link:**
   - Paste the OAuth2 URL into your browser

2. **Select Your Server:**
   - Choose the server you want to add the bot to
   - Note: You need **Manage Server** permission on that server

3. **Authorize the Bot:**
   - Click **Authorize**
   - Complete the CAPTCHA verification

4. **Verify Bot is Added:**
   - Your bot now appears in your server's member list
   - It should show as "offline" until you run the bot code

---

## Part 3: Discord Client Setup (Developer Mode and IDs)

To easily get the unique IDs for channels and servers, you need to enable Developer Mode in the Discord desktop or web client.

### Step 5: Enable Developer Mode

1. **Open Discord User Settings:**
   - Click the gear icon (⚙️) at the bottom left of Discord

2. **Navigate to Advanced Settings:**
   - Scroll down to **App Settings**
   - Click **Advanced**

3. **Enable Developer Mode:**
   - Toggle **Developer Mode** to **ON**

> 💡 **Alternative Path**: Settings → Advanced → Developer Mode

---

### Step 6: Copy Channel and Server IDs

After enabling Developer Mode, you can now copy IDs:

#### **Get Channel ID:**
1. Right-click on any text channel
2. Click **Copy Channel ID** at the bottom of the menu
3. The ID will be copied to your clipboard

```text
Channel ID: 987654321098765432
```

---

## 📊 Workflow Diagram

```
┌──────────────────────┐
│  1. Developer Portal │
│  Create Application  │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│   2. Add Bot User    │
│   Get Bot Token      │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│  3. OAuth2 URL Gen   │
│  Generate Invite URL │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│   4. Authorize Bot   │
│   Add to Server      │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│ 5. Enable Dev Mode   │
│   in Discord Client  │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│  6. Copy IDs         │
│  Channel & Server    │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│   ✅ Ready for       │
│      X401!           │
└──────────────────────┘
```

---

## 📝 Important Notes

- ✅ **Minimum Permissions**: Always grant the minimum permissions necessary for your bot's functionality
- ✅ **Developer Mode**: Must be enabled to copy IDs from Discord client
- ✅ **Server Permissions**: You need "Manage Server" permission to add bots
- ✅ **Bot Offline Status**: Bot appears offline until you run the bot code with the token
- ⚠️ **Token Regeneration**: If you accidentally expose your token, regenerate it immediately in the Developer Portal

---

## 🔧 Troubleshooting

### Problem: Can't see "Copy ID" option

**Solution**: Make sure Developer Mode is enabled in Discord settings (Settings → Advanced → Developer Mode).

### Problem: Bot appears offline after adding to server

**Solution**: This is normal. The bot will appear online only when you run your bot code with the correct token.

### Problem: "Missing Permissions" error when inviting bot

**Solution**: Ensure you have "Manage Server" permission on the server you're trying to add the bot to.



### Problem: Lost or forgot bot token

**Solution**: Go to Developer Portal → Your Application → Bot → Reset Token. You'll need to update your code with the new token.

### Problem: Bot immediately disconnects

**Solutions**:
- Verify the token is correct
- Check if required intents are enabled (Message Content Intent for reading messages)
- Review Discord API status for any outages

---

## 🎉 You're Done!

You now have all the credentials needed:
- ✅ **Bot Token** → from Discord Developer Portal
- ✅ **Channel ID** → from Discord Client (with Developer Mode)
- ✅ **Server ID** → from Discord Client (with Developer Mode)

These are all the credentials required for **X401** usage. You can now integrate your Discord bot with your application!

---

## 📚 Additional Resources

- [Discord Developer Documentation](https://discord.com/developers/docs/intro)
- [Discord Developer Portal](https://discord.com/developers/applications)

---
---

**Made with ❤️ for X401**