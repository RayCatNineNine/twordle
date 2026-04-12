# Twordle

A Wordle-style word guessing game for two, built as a single-page Progressive Web App (PWA). Guess the secret 5-letter word in 6 tries — each guess reveals which letters are correct, present but misplaced, or absent.

## Features

- **1,440 curated words** — common 5-letter English nouns, verbs, and adjectives (no proper nouns, no obscure words)
- **Installable PWA** — add it to your home screen and play offline
- **Responsive design** — automatically sizes to fit any screen, from small phones to desktop
- **Animated feedback** — tile flips, shakes, and bounces for a polished feel
- **Auto-clear on invalid words** — if your guess isn't in the word list, the tiles shake and clear automatically so you can retype immediately
- **Persistent stats** — tracks games played, wins, current streak, and best streak across sessions
- **Physical keyboard support** — works with on-screen tapping or a hardware keyboard

## How to Play

1. Type a 5-letter word and press **Enter**
2. Tiles flip to reveal clues:
   - 🟩 **Green** — correct letter in the correct position
   - 🟨 **Amber** — correct letter but in the wrong position
   - ⬛ **Grey** — letter is not in the word
3. Use the clues to narrow down your next guess
4. You have **6 tries** to find the word

## Project Structure

```
twordle/
├── index.html       ← entire app (HTML + CSS + JS in one file)
├── manifest.json    ← PWA manifest (app name, icons, theme)
├── sw.js            ← service worker for offline caching
├── icon-192.png     ← home screen icon (192×192)
├── icon-512.png     ← splash screen icon (512×512)
└── README.md        ← this file
```

## Deploying to an Android Phone

There are several ways to get Twordle running on your Android device.

### Option 1: Host on GitHub Pages (recommended)

This is the easiest way to share the app with anyone and get a real URL.

1. **Push the files to a GitHub repository** (if not already done)

2. **Enable GitHub Pages:**
   - Go to your repository on GitHub
   - Navigate to **Settings → Pages**
   - Under "Source", select **Deploy from a branch**
   - Choose the **main** branch and **/ (root)** folder
   - Click **Save**

3. **Wait a minute or two** — GitHub will publish your site at:
   ```
   https://<your-username>.github.io/<repo-name>/
   ```

4. **Install on your Android phone:**
   - Open the URL above in **Chrome** on your phone
   - Tap the **three-dot menu (⋮)** in the top right
   - Tap **"Add to Home screen"** or **"Install app"**
   - Twordle now appears as an app icon on your home screen and runs fullscreen

### Option 2: Local network (no internet needed)

Good for quick testing on your local Wi-Fi.

1. **Install a simple HTTP server** on your computer. If you have Python installed:
   ```bash
   cd /path/to/twordle
   python3 -m http.server 8000
   ```

2. **Find your computer's local IP** (e.g. `192.168.1.42`):
   ```bash
   # macOS / Linux
   hostname -I
   # or
   ifconfig | grep "inet "
   ```

3. **Open the URL on your phone:**
   - Make sure your phone is on the same Wi-Fi network
   - Open Chrome and go to `http://192.168.1.42:8000`
   - Note: "Add to Home screen" may not work over plain HTTP — use Option 1 for the full PWA experience

### Option 3: Direct file access

The simplest approach, but without PWA/offline features.

1. **Transfer `index.html`** to your phone (email it, use a file manager, USB cable, etc.)
2. **Open it in Chrome** — the game works as a standalone HTML file
3. Note: service worker and PWA install won't function from a `file://` URL

## Tech Stack

Everything is vanilla — no build tools, no frameworks, no dependencies:

- **HTML5** — semantic structure
- **CSS3** — custom properties, flexbox, grid, keyframe animations
- **Vanilla JavaScript** — ES6+, no libraries
- **Google Fonts** — Playfair Display (tiles) and DM Sans (UI)
- **Service Worker** — offline caching via Cache API
- **Web App Manifest** — PWA metadata for home screen install

## Credits

Created by **[Your Name]** and **Claude** (Anthropic).

- Game concept, design direction, and feature decisions by **[Your Name]**
- Code implementation, word list curation, and documentation by **Claude**

## License

Feel free to use, modify, and share this project.
