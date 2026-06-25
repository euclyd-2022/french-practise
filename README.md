# French Practice

A mobile-friendly web app for practising English-to-French translation, with AI-powered feedback focused on natural spoken French.

Built as a single `index.html` file — no framework, no build step, no server.

## What it does

You're given a short passage of everyday English and asked to translate it into French. When you submit, Claude analyses your translation and gives feedback focused on **lexical chunks** — phrases to learn as a whole rather than word by word (e.g. *"j'ai raté le bus"* rather than individual words for "miss" and "bus").

Feedback is organised into three levels:

- **Phrases to learn** — the main focus. Natural spoken French equivalents for chunks where your translation was unnatural or word-for-word from English. Where the formal written version differs meaningfully, that's noted too.
- **Grammar** — brief notes on tense, agreement, or word order errors.
- **Spelling & accents** — flagged lightly in amber. The app is designed for spoken fluency practice, so these are noted but not dwelt on.

Phrases you want to remember can be saved to a **phrase bank**, which persists in your browser between sessions. The phrase bank can be exported as an Anki flashcard file (`.txt`) for spaced repetition practice.

The app defaults to **casual spoken French** throughout — dropped *ne*, *on* instead of *nous*, contracted forms — because that's what you'd actually hear and say.

## Setup

### 1. Get an Anthropic or Gemini API key

Go to [console.anthropic.com](https://console.anthropic.com) or [aistudio.google.com/apikey](https://aistudio.google.com/apikey) , create an account, and generate an API key. You'll need to add a small credit balance under Billing before the key will work — a few pounds/dollars goes a long way at this usage level (each practice session costs a fraction of a penny).

### 2. Host the file

The simplest free option is **GitHub Pages**:

1. Create a new public GitHub repository
2. Upload `index.html` (and this `README.md` if you like)
3. Go to **Settings → Pages**, set the source to `main` branch and `/ (root)`
4. Your app will be live at `https://yourusername.github.io/your-repo-name` within a minute or two

### 3. Open on your iPhone

Navigate to your GitHub Pages URL in Safari. For the best experience, add it to your home screen: tap the share icon → **Add to Home Screen**. It'll open full-screen like a native app.

Enter your API key on the setup screen — it's saved in Safari's local storage and never leaves your device (it's only sent directly to `api.anthropic.com`).

## Phrase bank & Anki export

Saved phrases are stored in your browser's `localStorage`, tied to the URL you're hosting the app on. They persist between sessions as long as you don't clear Safari's website data.

To export to Anki, tap the download icon on the phrase bank screen. This generates a tab-separated `.txt` file that Anki can import directly:

- **Front:** French phrase
- **Back:** English equivalent, explanation note, and formal version (if applicable)
- Pre-configured for a `French Practice` deck, tagged `french spoken`

Import into Anki desktop via **File → Import**. On iPhone with AnkiMobile, use the share sheet to import directly.

## Notes

- The app uses `claude-sonnet-4-6` via the Anthropic API
- Your API key is stored in `localStorage` in your browser only
- The phrase bank is also stored in `localStorage` — clearing Safari's website data will wipe it, so export to Anki regularly if you want to keep your phrases
- The app works entirely client-side with no backend
