# QuestionGG Discord Bot

QuestionGG is a competitive trivia bot for Discord. It pulls questions from a customizable JSON bank, tests server members with timed trivia rounds, and tracks player scores on a live leaderboard. 

## Features
* **Automated Trivia Rounds:** Serves questions sequentially with a strict 30-second response window[cite: 3, 4].
* **Live Leaderboard Tracking:** Automatically updates and sorts player scores based on correct answers and total participation[cite: 3, 4, 5].
* **Local JSON Database:** Easily add, edit, or remove questions directly via `questions.json` without touching the bot's core logic[cite: 7].
* **Slash Command Integration:** Fully synced application commands for modern Discord UI interaction[cite: 4].

## Prerequisites
* Python 3.8+
* Discord Developer Account & Bot Token

## Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/rayhan09niloy/questiongg-discord-bot.git
   cd questiongg-discord-bot


2. **Install dependencies:**
```bash
pip install -r require.txt

```

*(Installs discord.py, python-dotenv, requests, asyncio, and aiohttp)*.


3. **Configure the Questions:**
Add your trivia data to `questions.json`. Each entry requires a `no` (index), `question`, and `answer`.


4. **Launch the Bot:**
Run the updated version of the script:
```bash
python botv1.1.py

```



## Commands

* `/start_contest` — Initiates the trivia round, displaying the current question and waiting 30 seconds for the first correct matching answer.
* `/leaderboard` — Displays the top 99 players sorted by accumulated points.



## Data Storage

* `questions.json`: The question bank.
* `leaderboard.json`: Persistent storage for user scores and metrics.
* `current_question.json`: Tracks the active question index to ensure sequential delivery across bot restarts.
* 

### Configuration Checklist

Follow these exact steps to make the bot operational:

1. **Enable Gateway Intents:** Go to the Discord Developer Portal, select your bot, navigate to the "Bot" tab, and toggle on the **Message Content Intent**. The bot requires this to read user answers in the chat[cite: 3, 4].
2. **Insert Bot Token:** Open `botv1.1.py` and locate `bot.run('')` at the bottom of the script. Paste your Discord bot token inside the quotation marks[cite: 4]. 
3. **Format Question Data:** Ensure `questions.json` follows the exact schema provided in the repository (an array of objects containing `no`, `question`, and `answer`)[cite: 7].
4. **Run Version 1.1:** Execute `botv1.1.py` instead of `bot.py`. The updated script includes app command synchronization (`self.tree.sync()`), which is required for modern Discord slash commands to appear in your server[cite: 4].
