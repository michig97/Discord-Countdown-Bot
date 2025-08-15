# Discord Countdown Bot

Ein einfacher **Discord-Bot** mit Mini-GUI, der täglich die **verbleibenden Tage** bis zu einem Event postet.

Am Event-Tag schaltet er in den **Hype-Modus** und postet **10×** zur Feier des Tages (30 s Abstand).

Entwickelt und getestet auf einem Raspberry Pi 4 2GB.

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
- Discord **Bot-Token** & **Channel-ID**
- **requirements.txt** erstelle ich händisch in folgendem Pfad "/home/user/Discord-Countdown-Bot"

Inhalt von requirements.txt
```
discord.py==2.4.0
```


# Installationsanleitung


Repository klonen
```bash
git clone https://github.com/michig97/Discord-Countdown-Bot.git
```

Wechselt in das Projektverzeichnis, in dem der Bot-Code liegt.
```bash
cd ~/Discord-Countdown-Bot
```

Erstellt eine neue Python-virtuelle Umgebung im Ordner ".venv".
```bash
python3 -m venv .venv
```

Aktiviert die virtuelle Umgebung
```bash
source .venv/bin/activate
```

Installiert alle in der Datei "requirements.txt" aufgelisteten Python-Pakete
innerhalb der virtuellen Umgebung.
```bash
python -m pip install -r requirements.txt
```

Startet den Bot über die Python-Datei "Code" im aktuellen Verzeichnis.
Falls die Datei "Code.py" heißt, sollte hier "python Code.py" stehen.
```bash
python Code
```

# Code in Binary umwandeln

Wechselt in das Projektverzeichnis, in dem der Bot-Code liegt.
```bash
cd ~/Discord-Countdown-Bot
```

Aktiviert die zuvor erstellte virtuelle Umgebung, 
damit die Installation und der Build in dieser Umgebung erfolgen.
```bash
source .venv/bin/activate
```

PyInstaller wird verwendet, um den Python-Code in eine eigenständige 
ausführbare Datei (Binary) zu verpacken
```bash
pip install pyinstaller
```

Baut aus der Datei "Code" ein einzelnes ausführbares Binary.
```bash
pyinstaller --onefile --noconsole --name DiscordCountdown ./Code
```

# Desktop-Shortcut erstellen

```bash
cat > ~/Desktop/discord-countdown-bot.desktop << 'EOF'
[Desktop Entry]
Type=Application
Name=Discord Countdown Bot
Exec=/home/user/Discord-Countdown-Bot/dist/DiscordCountdown
Path=/home/user/Discord-Countdown-Bot
Terminal=false
EOF
```
