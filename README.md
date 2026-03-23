# 🚀 MathQuest — Agentic Math Tutor

A Kumon-style math adventure tutor for kids, built with a single HTML file. No frameworks, no installs — just open in a browser.

---

## ✨ Features

- **Placement Quiz** — 10 questions to find the right starting level automatically
- **10 Levels** — Addition → Subtraction → Multiplication → Division → Mixed Operations
- **Game Layer** — XP points, streaks, level-ups, confetti, and character selection
- **4 Guide Characters** — Nova 🤖, Blaze 🐉, Cosmo 👾, Foxy 🦊
- **AI Hints** — Claude Haiku gives personalized hints on demand (costs ~$0.001 each)
- **Parent Dashboard** — PIN-protected view with accuracy stats by operation type
- **Mastery-based** — Must score 8/10 to advance, just like Kumon
- **Persistent Progress** — Saves to browser localStorage across sessions

---

## 🚀 Quick Start (Local)

1. Download `index.html`
2. Open it in **Chrome** or any modern browser (double-click the file)
3. Enter your Anthropic API key and set a 4-digit parent PIN
4. Your child picks their guide character and takes the placement quiz
5. Done!

---

## 🌐 Deploy to GitHub Pages (Free Hosting)

Give your child their own URL (e.g. `yourname.github.io/mathquest`):

### Step 1 — Create the repo
```bash
git init
git add index.html README.md
git commit -m "Initial MathQuest"
```

### Step 2 — Push to GitHub
```bash
gh repo create mathquest --public --push --source=.
# or via GitHub.com: create repo → push manually
```

### Step 3 — Enable GitHub Pages
1. Go to your repo on GitHub
2. Click **Settings** → **Pages**
3. Under "Source" select **Deploy from a branch** → `main` → `/ (root)`
4. Click **Save**
5. Wait ~60 seconds → your app is live at `https://yourusername.github.io/mathquest`

---

## 🔑 API Key Setup

The app calls Anthropic's API **only for hints** — everything else (problem generation, answer checking, XP, levels) runs in JavaScript for free.

**Cost estimate:** ~$0.001 per hint. If your child asks for 10 hints/day, that's ~$0.30/month.

### Get your API key:
1. Go to [console.anthropic.com](https://console.anthropic.com)
2. Create an account → **API Keys** → **Create Key**
3. Copy the key (starts with `sk-ant-...`)

### Where to enter it:
- The app asks for it on first launch in the **Parent Setup** screen
- It's stored in **localStorage** (browser only — never in the repo or sent anywhere except Anthropic)
- ⚠️ **Never commit your API key to GitHub**

---

## 🔒 Security Notes

| What | Where it's stored | Safe to share? |
|---|---|---|
| API Key | Browser localStorage | ✅ Never in repo |
| Parent PIN | Browser localStorage | ✅ Never in repo |
| Child's progress | Browser localStorage | ✅ Local only |

- Progress is **per-device** (localStorage doesn't sync across devices)
- If your child uses multiple devices, progress won't carry over
- To reset: Parent Dashboard → Reset All Progress

---

## 📊 Curriculum Map

| Level | Topic | Range |
|---|---|---|
| 1 | Addition Basics | 1–10 |
| 2 | Addition Challenge | 1–20 |
| 3 | Subtraction Basics | 1–15 |
| 4 | Subtraction Challenge | 1–25 |
| 5 | Mixed Add & Subtract | 1–30 |
| 6 | Multiplication Intro | ×1–5 |
| 7 | Multiplication Tables | ×1–10 |
| 8 | Division Basics | ÷2–5 |
| 9 | Division Challenge | ÷2–10 |
| 10 | Mixed Operations | All |

**Advancement rule:** Score 8/10 correct on a set AND earn enough XP → level up.

---

## 🛠️ Customization

Everything is in `index.html`. Easy things to change:

```javascript
// Change pass threshold (default: 8/10)
const PASS_THRESHOLD = 8;

// Change set size (default: 10 problems)
const SET_SIZE = 10;

// Add your own character
const CHARACTERS = [
  { name: 'Nova', emoji: '🤖', phrases: ['...'] },
  // add more here
];
```

---

## 🗺️ Roadmap Ideas

- [ ] Reading comprehension module
- [ ] Writing prompts module
- [ ] Decimal & fractions levels
- [ ] Word problem generator (AI-powered)
- [ ] Weekly email report for parents
- [ ] Multi-child support
- [ ] Sync progress via Airtable or Google Sheets

---

## 📁 Repo Structure

```
mathquest/
├── index.html    ← The entire app (HTML + CSS + JS)
└── README.md     ← This file
```

No dependencies. No build step. No node_modules. Just one file.

---

Built with ❤️ using vanilla HTML/CSS/JS + Claude Haiku API.
