# 🤖 Paradox Bot

A multi-purpose, high-performance Discord bot built with Python, `discord.py`, and MongoDB. Specially designed for large gaming communities with built-in support for carry services, helper applications, advanced moderation, and a fully featured economy system with interactive casino games.

---

## ✨ Features

### 🎟️ Ticket & Helper Systems
| Feature | Description |
|---|---|
| **Carry Service** | Interactive menus for members to request carries in multiple games (ALS, AV, ASTD, etc). |
| **Helper Applications** | Automated application forms for players to apply for helper/booster roles. |
| **Vouch System** | Allow users to vouch for helpers/staff. Tracks vouch count and auto-calculates Vouch Levels. |
| **Macro Support** | Dedicated tickets for purchasing or setting up gaming macros. |

### 🪙 Paradoxy Economy & Casino
| Feature | Description |
|---|---|
| **Interactive Games** | Full UI-based **Poker**, **Blackjack**, and **Heists** with real-time state updates. |
| **Game Penalties** | Anti-stall mechanics: Inactivity results in folding (Poker) or jail/loss (Blackjack/Heists). |
| **Rigged Odds** | Dynamic win rates influenced by inventory items like "Lucky Coin" or "Golden Clover". |
| **Banking & Loans** | Hourly variable interest rates and a loan system for quick cash. |
| **Daily Quests** | Trackable objectives (Gamble, Work, Crime) with automated rewards. |

### 🏆 Leveling & Kingdom Ranks
| Feature | Description |
|---|---|
| **XP System** | Earn XP through active messaging and staying in voice channels. |
| **Kingdom Roles** | Tiered roles (Peasant to Paradox Overlord) are auto-created and assigned every 5 levels. |
| **Leaderboards** | Global and local rankings for both wealth and XP. |

### 🛡️ Security & Moderation
| Feature | Description |
|---|---|
| **Swear Word Filter** | Auto-deletes messages with banned words and manages a tiered punishment system. |
| **Anti-Scam / Phishing** | Detects and instantly deletes malicious links with a strike-based auto-ban system. |
| **Quarantine System** | Temporarily traps suspicious users in a restricted channel until review. |
| **Log Whitelist** | Advanced whitelist to allow specific users/admins to bypass filters and logging. |

### 💎 Server & Community
| Feature | Description |
|---|---|
| **Server Boosting Rewards** | Beautiful custom embeds and auto-assigned roles for server boosters. |
| **Interactive Boost Roles** | Allows boosters to select their own custom colored role from a dropdown! |
| **Social & Marriage** | Propose to members, track marriages, and use dozens of interactive social commands. |
| **Custom Greetings** | Highly customizable Welcome/Goodbye embeds with banner images. |

---

## 🚀 Setup & Installation

## 🚀 Deployment (Render.com)
Paradox Bot is now optimized for **Render.com** hosting.

1. **Environment Variables**:
   - `DISCORD_TOKEN`: Your bot token from the Discord Developer Portal.
   - `MONGO_URI`: Your MongoDB Atlas connection string.
   - `PORT`: (Automatic) Set by Render, used for the keep-alive server.
2. **Build Settings**:
   - Runtime: `Python 3.13`
   - Build Command: `pip install -r requirements.txt`
   - Start Command: `python bot_main.py`
3. **Uptime**:
   - Set up a monitor (e.g., UptimeRobot) to ping your Render URL every 5 minutes to prevent the bot from sleeping.

## 🛡️ Moderation & Advanced Config
We have added professional-grade tools for server management:

- **`!viewconfig`**: Displays a comprehensive overview of all server rules, punishment tiers, and economy cooldowns.
- **`!setbypass <@user/role>`**: Grants "Global Bypass" permissions, allowing trusted members to use restricted commands without limits.
- **`!setgif <action> <url>`**: Customize the visual experience by changing GIFs for flavor commands like `!annihilate`.
- **`!setcooldown <cmd> <time>`**: Dynamic control over economy command frequencies.
- **`!settier <1.1-1.5> <time>`**: Granular control over the duration of rule-based punishments.

## ⚙️ Interactive Setup
The bot now features a built-in **📖 Setup Guide** directly in the `!help` menu. This guide provides a step-by-step walkthrough for configuring welcome messages, logs, and ticket systems.
 with `Administrator` permissions.

### 2. Configure Local Settings
Fill in your `config.json` (most settings can be configured via Discord commands later):
```json
{
    "TOKEN": "paste-your-bot-token-here",
    "PREFIX": "!",
    "AUTO_ROLE_NAME": "Member",
    "WELCOME_CHANNEL_ID": 123456789
}
```

### 3. Database Setup (MongoDB)
1. Add `MONGO_URI` as an environment variable (MongoDB Atlas connection string).
2. Start the bot.
3. Run `!migrate db` inside Discord to transfer old legacy data into the cloud.

### 4. Install & Run
```bash
pip install -r requirements.txt
python bot_main.py
```

---

## 📋 Essential Commands

Type `!help paradox` in Discord for a fully interactive menu!

### ⚙️ Setup & Economy (Admin)
| Command | Description |
|---|---|
| `!setwelcomechannel <#ch>`| Set where greetings go |
| `!setlogchannel <#ch>` | Set where logs go |
| `!reseteco <@user/all>` | Reset economy data (Owner only) |
| `!setlevel <@user> <num>` | Set exact level/XP for a user |
| `!setrank <lvl> <name>` | Customize kingdom role names |

### 🪙 Economy & Casino (User)
| Command | Description |
|---|---|
| `!balance` | View wallet, bank, and active status effects |
| `!poker <min> <max>` | Start an interactive Poker game |
| `!bj <bet>` | Play Blackjack (30s action limit) |
| `!heist` | Start a strategic heist (Lockpick/Circuit/Safe) |
| `!quests` | View and claim daily quest rewards |
| `!shop` | Buy items to boost your luck or earnings |

### 🛡️ Security & Moderation
| Command | Description |
|---|---|
| `!togglefilter` | Toggle swear detection |
| `!purge <num>` | Delete bulk messages (1-100) |
| `!mute <@user> <min>` | Timeout a member |
| `!quarantine <@user>` | Send to quarantine manually |
| `!testjoin / !testleave` | Simulate greeting events (Admin only) |

---

## 📁 File Structure

```
├── bot_main.py        # Main bot entry point (events + commands)
├── bot_functions.py   # Helper functions (filter logic, formatting)
├── bot_database.py    # Asynchronous MongoDB wrapper
├── config.json        # Bot configuration (menus, token, settings)
├── requirements.txt   # Python dependencies
└── README.md          # This file
```

