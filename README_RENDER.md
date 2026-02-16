# 🤖 AterBot für Render.com - 24/7 Deployment

Dein Minecraft AFK-Bot läuft jetzt 24/7 auf Render.com (kostenlos)!

## 📋 Voraussetzungen

1. **GitHub Account** - https://github.com/signup
2. **Render.com Account** - https://render.com/register
3. **Aternos Minecraft Server** mit `online-mode: false`

---

## 🚀 Schritt-für-Schritt Anleitung

### 1️⃣ Projekt zu GitHub hochladen

1. Gehe zu https://github.com/new
2. Repository Name: `aterbot-24-7` (oder beliebiger Name)
3. Wähle **Public** (für kostenloses Render)
4. Klicke **Create repository**

5. Lade alle Dateien aus diesem Ordner hoch:
   - Gehe in dein neues Repository
   - Klicke auf **Add file** → **Upload files**
   - Ziehe ALLE Dateien aus diesem Ordner in das Upload-Fenster
   - Klicke **Commit changes**

---

### 2️⃣ Konfiguration anpassen

**WICHTIG:** Bevor du deployst, bearbeite die `config.json` Datei auf GitHub:

1. Öffne die Datei `config.json` in deinem Repository
2. Klicke auf das Stift-Symbol (Edit)
3. Ändere diese Werte:

```json
{
	"client": {
		"host": "DEIN-SERVER.aternos.me",  ← Ändere das!
		"port": "12345",                    ← Ändere das!
		"username": "DEIN-BOT-NAME"         ← Ändere das!
	},
	...
}
```

4. Klicke **Commit changes**

---

### 3️⃣ Auf Render.com deployen

1. Gehe zu https://render.com/
2. Melde dich an
3. Klicke **New +** → **Web Service**
4. Verbinde dein GitHub Konto (wenn nötig)
5. Wähle dein `aterbot-24-7` Repository
6. Klicke **Connect**

**Einstellungen:**
- **Name:** `aterbot` (oder beliebig)
- **Region:** Frankfurt (am nächsten zu Deutschland)
- **Branch:** `main`
- **Build Command:** `npm install`
- **Start Command:** `npm start`
- **Plan:** **Free** ✅

7. Klicke **Create Web Service**

---

### 4️⃣ Bot vorbereiten

**Während Render deployt (dauert 2-3 Minuten):**

1. Starte deinen Aternos Server
2. Gehe mit deinem Minecraft Client auf den Server
3. Baue einen **Bedrock-Raum** (Größe: 5x3x5 Blöcke)
4. Warte bis der Bot joined
5. **WICHTIG:** Teleportiere den Bot in den Raum:
   ```
   /tp BOT-NAME ~ ~ ~
   ```
6. **WICHTIG:** Setze Bot auf Creative:
   ```
   /gamemode creative BOT-NAME
   ```

---

## ✅ Fertig!

Dein Bot läuft jetzt **24/7 kostenlos** auf Render.com!

### 📊 Bot Status überprüfen

- Öffne die URL deines Render Services (z.B. `https://aterbot.onrender.com`)
- Du siehst eine Status-Seite mit grünem Punkt = Bot läuft!

### 📝 Logs ansehen

1. Gehe zu deinem Render Dashboard
2. Klicke auf deinen Service
3. Klicke auf **Logs** Tab
4. Du siehst: `AFKBot logged in <name>`

---

## ⚠️ Wichtige Hinweise

### Bot wird nach 15 Minuten gebannt?
Aternos erkennt AFK-Bots. Lösungen:
1. Entbanne den Bot: `/pardon BOT-NAME`
2. Deaktiviere AFK-Kick auf deinem Server
3. Der Bot verbindet sich automatisch neu

### Bot verbindet sich nicht?
1. Prüfe ob dein Aternos Server läuft
2. Prüfe `config.json` - Host und Port korrekt?
3. Prüfe Render Logs auf Fehler

### Server geht offline?
Render startet den Bot automatisch neu! Der Bot versucht alle 15 Sekunden sich zu verbinden.

---

## 🔄 Änderungen vornehmen

Wenn du etwas ändern willst:

1. Bearbeite die Dateien auf GitHub
2. Render deployt automatisch neu (dauert ~2 Minuten)

---

## 💰 Kostenlos vs. Bezahlt

**Free Tier (aktuell):**
- ✅ 750 Stunden pro Monat (= 24/7)
- ✅ Automatische Neustarts
- ✅ Logs

**Wenn der Free Tier nicht reicht:**
- Render kostet ab $7/Monat für garantiert 24/7
- Oder nutze mehrere Free Accounts 😉

---

## 🆘 Support

Problem? Prüfe die Logs auf Render.com!

**Häufige Fehler:**
- `ECONNREFUSED` → Server ist offline
- `Invalid move player packet` → Bot ist aus dem Raum entkommen
- `unsupported protocol` → Deine Minecraft Version wird nicht unterstützt

---

**Viel Spaß mit deinem 24/7 Bot! 🎮**
