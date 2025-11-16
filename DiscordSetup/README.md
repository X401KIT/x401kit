# Discord Bot Creation and Server Setup: A Step-by-Step Guide

This guide walks you through creating a Discord application, adding a bot user, generating an invite link, adding the bot to your server, and enabling Developer Mode to copy essential IDs.

---

## Part 1: Create the Discord Application and Bot User

The Discord Developer Portal is the central hub for creating and managing all your Discord applications and bots.

### Step 1: Create a New Application

- **Go to the Developer Portal:** Navigate to the Discord Developer Portal and log in with your Discord account.  
- **Click "New Application":** In the top right corner.  
- **Name the Application:** Enter a name for your application (this will be the bot's display name). Click **Create**.  
---

### Step 2: Add a Bot User and Get the Token

- **Navigate to the Bot Tab:** On the left sidebar, click the **Bot** tab.  
- **Add the Bot:** Click **Add Bot** → confirm with **Yes, do it!**  
- **Get the Bot Token (Important):**  
  - Click **Reset Token** under the Token section.  
  - Copy it immediately and save it securely.  
- **Enable Privileged Gateway Intents:**  
  - create instant invite 
      
- **Save Changes.**

---

## Part 2: Generate the Invite Link and Add to Server

You must use the OAuth2 URL Generator to create a unique link that invites your bot with the correct permissions.

### Step 3: Generate the OAuth2 Invite Link

- Go to **OAuth2 → URL Generator**.  
- **Select Scopes:**
  - `bot`
  - Avoid **Administrator** unless truly required.  
 **Copy the URL:** The invite URL at the bottom updates automatically.

---

### Step 4: Invite the Bot to Your Server

- Paste the invite URL in your browser.  
- Select the server you want to add the bot to (requires **Manage Server** permission).  
- Click **Authorize** → Complete CAPTCHA.  
- Your bot now appears  in your server's member list 

---

# Part 3: Discord Client Setup (Developer Mode and Channel IDs)

To easily get the unique IDs for  channels,  you need to enable Developer Mode in the Discord desktop or web client.

### Step 5: Enable Developer Mode

- Open **User Settings (⚙️)**.  
- Go to **Advanced**.  
- Toggle **Developer Mode** ON.

---

### Step 6: Copy Channel and Server IDs

After enabling Developer Mode:

- **Copy Channel ID:** Right-click a channel → **Copy ID**  


---

You now have all the credentials and IDs needed to start using your Discord bot! via X401 protocol
