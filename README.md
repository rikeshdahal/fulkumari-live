# Fulkumari Live 🎙️ 
**Live Preview [FULKUMARI_LIVE](https://rikeshdahal.github.io/fulkumari-live/)**

A real-time AI voice + vision companion powered by **Google Gemini Live API** and the **TalkingHead** avatar engine. Talk to an animated 3D avatar that listens, sees (via your camera), and responds — in **English or Nepali**.

**Built by [Rikesh Dahal](https://github.com/rikeshdahal)**

---

## ✨ Features

- 🎤 **Real-time voice conversation** — speaks and listens simultaneously
- 👄 **Amplitude-driven lip-sync** — mouth moves in exact sync with audio (PCM RMS analysis, not text guessing)
- 📝 **Live captions** — streaming word-by-word transcript
- ⏱️ **Synced subtitles** — subtitle appears exactly when the audio plays, not before
- 📷 **Camera vision** — Gemini can see and describe your camera feed
- 🌐 **Multilingual** — auto-detects Nepali / English / mixed code-switching
- 🔑 **No backend needed** — pure frontend, single HTML file
- 🔐 **API key in-browser** — key never hardcoded, stored in sessionStorage only (cleared on tab close)
- 🧑‍🎤 **Two avatars** — Fulkumari (female, Zephyr voice) & Rikesh (male, Fenrir voice)

---

## 🚀 Quick Start

### Option 1 — Open directly (easiest)
```bash
# Just open the file in Chrome / Edge / Firefox
open index.html
```
> **Note:** Some browsers block microphone access on `file://` URLs. Use Option 2 if that happens.

### Option 2 — Serve locally
```bash
# Python (built-in, no install needed)
python3 -m http.server 8080
# then open http://localhost:8080

# OR Node.js
npx serve .
```

### Option 3 — GitHub Pages / Netlify / Vercel
Just push the repo and enable static hosting. No build step required.

---

## 🔑 API Key Setup

1. Go to [aistudio.google.com/app/apikey](https://aistudio.google.com/app/apikey)
2. Create a free Gemini API key
3. Open the app — enter your key in the prompt
4. The key is stored in `sessionStorage` only — it clears when you close the tab

> ⚠️ **Never commit your API key.** The app is designed so the key is always entered at runtime, never in code.

---

## 📁 Project Structure

```
fulkumari-live/
├── index.html      # The entire app — single self-contained file
├── LICENSE         # MIT
└── README.md       # This file
```

No npm, no bundler, no build step. Everything runs in the browser via ES modules and CDN imports.

---

## 🛠️ Customisation

### Change avatar models
Edit the `AV` config object in the `<script>` section:
```js
const AV = {
  fulkumari: {
    glb:   'https://your-cdn.com/your-avatar.glb',  // any Ready Player Me GLB
    voice: 'Zephyr',   // Gemini voice name
    name:  'Fulkumari',
  },
  rikesh: { ... }
};
```

### Change AI voice
Supported Gemini voices: `Zephyr`, `Fenrir`, `Charon`, `Kore`, `Aoede`  
Edit the `voice` field in the `AV` config.

### Change persona / system prompt
Edit the `systemInstruction` string in `startSession()` to give your avatar a different personality, language, or knowledge domain.

### Add more avatars
Add a new entry to `AV`, add a card in the sidebar HTML with `data-person="yourkey"`, and it just works.

---

## 🧰 Tech Stack

| Layer | Library |
|---|---|
| AI Voice + Vision | [Google Gemini Live API](https://ai.google.dev/gemini-api/docs/live) |
| 3D Avatar | [TalkingHead](https://github.com/met4citizen/TalkingHead) |
| 3D Rendering | [Three.js](https://threejs.org/) r180 |
| Lip-sync | PCM amplitude analysis (custom, no external lib) |
| Fonts | DM Sans + DM Mono (Google Fonts) |

---

## 🌐 Browser Support

| Browser | Support |
|---|---|
| Chrome 120+ | ✅ Full |
| Edge 120+ | ✅ Full |
| Firefox 120+ | ✅ Full |
| Safari 17+ | ⚠️ Partial (AudioWorklet may need flag) |
| Mobile Chrome | ✅ Works |

Requires microphone permission. HTTPS required for production deployment (localhost is fine for dev).

---

## 🤝 Contributing

Pull requests welcome! Some ideas:

- [ ] More avatar options
- [ ] Conversation history / export
- [ ] Custom wake word
- [ ] Emotion-driven avatar expressions
- [ ] PWA / installable app

Please open an issue before large PRs to discuss direction.

---

## 📄 License

**Attribution Required** — Free to use, modify, and distribute.  
You must give credit to the original author in your UI and source code.

> Based on [Fulkumari Live](https://github.com/rikeshdahal/fulkumari-live) by Rikesh Dahal

See the [LICENSE](./LICENSE) file for full terms.  
TL;DR: Use it freely. Just don't pretend you made it.

---

## 🙏 Credits

- [TalkingHead](https://github.com/met4citizen/TalkingHead) by met4citizen — avatar engine
- [Google Gemini](https://deepmind.google/technologies/gemini/) — AI model
- Avatar models hosted via [jsDelivr](https://www.jsdelivr.com/)
