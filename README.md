# Discord Countdown Bot

Ein einfacher **Discord-Bot** mit Mini-GUI, der täglich die **verbleibenden Tage** bis zu einem Event postet.  
Am Event-Tag schaltet er in den **Hype-Modus** und postet **10×** zur Feier des Tages (30 s Abstand).

## Features
- **Täglicher Countdown** in einen Textkanal
- **Event-Day Hype**: 10 Posts am Event-Tag (30 s Abstand)
- **Optionales `@everyone`** (per Checkbox, wenn der Bot die Berechtigung hat)
- **Post-Zeit in HH:MM** (z. B. `04:20`)
- **Bildanhang** optional (wird mit jeder Nachricht gesendet)
- **GUI** (Tkinter) für Token, Channel-ID, Event-Name/Datum, Uhrzeit, @everyone, Bild
- **Cross-Platform**: Raspberry Pi / Linux / Windows (PyInstaller-Builds)

## Anforderungen
- Python **3.11+**
- Tkinter (unter Debian/RPi: `sudo apt install -y python3-tk`)
- Discord **Bot-Token** & **Channel-ID**

```
requirements.txt
discord.py==2.4.0
```

## Konfiguration

> **Tipp (RPi/Debian):**
> ```bash
> sudo apt update
> sudo apt install -y python3-tk
> ```

Die Datei **`config.json`** liegt **im selben Ordner** wie Script/Binary und wird von der GUI gelesen/geschrieben:
```json
{
  "token": "YOUR_DISCORD_BOT_TOKEN",
  "channel_id": "123456789012345678",
  "event_name": "My Festival",
  "event_date": "2025-08-14",
  "post_hour": "9:00",
  "mention_everyone": false,
  "image_path": "path/to/image.png",
  "last_post_date": ""
}
```

## Start (Raspberry Pi / Linux)
```
1. Repository klonen
git clone https://github.com/michig97/Discord-Countdown-Bot.git
cd Discord-Countdown-Bot

2. Virtuelle Umgebung erstellen
python3 -m venv .venv
source .venv/bin/activate

3. Abhängigkeiten installieren
pip install -r requirements.txt

4. Bot starten
python3 Code
```

## Native Binary bauen (Raspberry Pi)

```
source .venv/bin/activate
pip install pyinstaller
pyinstaller --onefile --noconsole --name DiscordCountdown Code
./dist/DiscordCountdown
```

## Optionaler Desktop-Shortcut:

```
[Desktop Entry]
Type=Application
Name=Discord Countdown Bot
Exec=/full/path/to/dist/DiscordCountdown
Terminal=false
```
