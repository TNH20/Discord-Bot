This is a discord bot i have created, the usage is pretty simple and i will be adding a guide on how to use the bot on my website https://tomhserver.co.uk/bot.html.
Discord Bot
A feature-packed Discord bot built with Python using `discord.py` and `yfinance`. Includes a roulette gambling system, reminders, polls, stock market lookups, server info, and more.
---
Features
Roulette – Bet virtual currency on numbers, colours, or even/odd
Economy System – Earn money by working or... other means
Stock Market – Look up live stock prices and historical data
Reminders – Set timed reminders in any channel
Polls – Create emoji-reaction polls with up to 10 options
Scoreboard – See who's richest on the server
Server Info – Display detailed server statistics
---
Requirements
Python 3.8+
A Discord bot token (create one here)
Python Dependencies
```bash
pip install discord.py yfinance
```
---
Setup
Clone or download the bot files.
Add your bot token — open `bot.py` and replace the placeholder:
```python
   BOT_TOKEN = "YOUR TOKEN HERE"
   ```
Create required channels in your Discord server:
`bot-channel` — the bot announces itself here on startup
`welcome` — new member greetings are sent here
`stock-market` — automatic stock price alerts go here
Run the bot:
```bash
   python bot.py
   ```
---
Commands
Command	Usage	Description
`!hello`	`!hello`	The bot greets you (rudely)
`!serverinfo`	`!serverinfo`	Displays server stats in an embed
`!remind`	`!remind 10 m Take a break`	Sets a reminder. Units: `s`, `m`, `h`
`!roulette`	`!roulette 100 red`	Bet on a number (0–36), colour (red/black), or even/odd
`!balance`	`!balance`	Check your current virtual balance
`!work`	`!work`	Earn a random amount of virtual currency
`!slut`	`!slut`	Risky command — win or lose a random amount
`!scoreBoard`	`!scoreBoard`	Shows a leaderboard of all user balances
`!poll`	`!poll "Question" "A" "B" "C"`	Creates a reaction poll (2–10 options)
`!stock`	`!stock AAPL 1d`	Look up stock data. Time periods: `1d`, `1mo`, `1y`, etc.
---
Economy System
Every user starts with 1,000 units of virtual currency. Balances reset if the bot restarts (no persistent storage by default).
`!work` – Earn between 100 and 10,000 units
`!roulette` – Gamble your balance
`!slut` – 50/50 chance to win or lose 1,000–20,000 units
---
Known Issues / Limitations
Balances are stored in memory only — they reset when the bot restarts
The `!slut` command has variable reference bugs and may not function correctly
Stock auto-alerts (`stockCheck` loop) may not start automatically — call `stockCheck.start()` after bot is ready
The welcome message event (`on_member_join`) has a missing `ctx` parameter and may not work out of the box
---
File Structure
```
bot.py          # Main bot file — all commands and logic
README.md       # This file
```
---
License
This project is personal/educational. Use at your own risk.
