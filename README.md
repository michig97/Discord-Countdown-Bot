# Discord-Countdown-Bot
A simple Discord bot that keeps counting down the days
# Features
Daily Countdown: Posts how many days are left until the event.

Event Day Hype: Sends 10 celebratory messages on the event day.

@everyone Option: Optional checkbox to ping all members.

Custom Post Time: Set posting time down to the minute (HH:MM).

Image Attachment: Optionally attach an image to the daily post.

GUI Configuration: Easy setup for event name, date, channel ID, token, and more.

Cross-Platform: Runs on Raspberry Pi, Linux, and Windows (supports PyInstaller builds).
# Requirements
Python 3.11+

discord.py 2.4.0

Tkinter (pre-installed with most Python distributions)

A Discord Bot Token & Channel ID

# Configuration
The bot uses a config.json file in the same folder as the script/executable:
"token": "YOUR_DISCORD_BOT_TOKEN",

"channel_id": "123456789012345678",

"event_name": "My Festival",

"event_date": "2026-07-24",

"post_hour": "9:00",

"mention_everyone": false,

"image_path": "path/to/image.png",

"last_post_date": ""
# Raspberry Pi Build
pyinstaller --onefile --noconsole --name DiscordCountdown discordbot.py
