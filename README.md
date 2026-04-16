⏱ Countdown Timer (Link-Based + Builder)

A minimal, self-contained countdown timer that doubles as a link generator.

You open the page → configure a date → get a URL → embed or share it anywhere.
No backend. No dependencies. No patience required.

🚀 Features
Single HTML file (no build step, no framework)
Countdown via URL parameters (?end=...)
Built-in link generator (builder UI)
Works standalone or embedded (Notion, iframes, etc.)
Real-time ticking (1s interval)
Automatic “Time’s Up” state
Clean, responsive UI
Clipboard copy support
🧠 How It Works

Two modes:

1. Builder Mode (default)

If no ?end= parameter exists:

Shows UI to input date + optional title
Generates a shareable countdown URL
2. Countdown Mode

If ?end= is present:

Parses date from URL
Starts ticking countdown
Displays remaining time
🔗 URL Format
?end=YYYY-MM-DDTHH:mm

Optional:

&title=Your Event Name
Example:
https://yourdomain.com/index.html?end=2026-01-01T00:00&title=New%20Year
📦 Usage
Option 1 — Direct Use

Just open the HTML file in your browser.

Option 2 — Host It

Upload to:

GitHub Pages
Netlify
Vercel
Any static hosting
Option 3 — Embed

Use in iframe:

<iframe src="YOUR_URL?end=2026-01-01T00:00" width="100%" height="300"></iframe>
⚠️ Known Limitations (Yes, they exist)
Uses local browser timezone
→ No explicit timezone handling
datetime-local input has no timezone metadata
Countdown accuracy depends on system clock
No persistence (no saved configs)
No support for past dates (auto clamps to zero)
🛠️ Internal Logic (for people who care)
Time difference:
diff = endTime - Date.now()
Decomposition:
days = diff / 86400000
hours = remainder / 3600000
minutes = remainder / 60000
seconds = remainder / 1000
Update loop:
setInterval(tick, 1000)
Stops when:
diff === 0
🧪 Edge Cases Handled
Invalid date → shows error message
Past date → stops immediately + shows "Time’s Up"
Empty input → blocked in builder
Clipboard fallback for insecure contexts
🧹 Why This Exists

Because most countdown tools:

require accounts
inject branding
overcomplicate basic logic

This does exactly one thing:

count time down, without drama

📁 File Structure
index.html   ← everything lives here (CSS + JS inline)
🔧 Possible Improvements

If you feel like evolving it beyond “simple but functional”:

Add timezone support (proper parsing, not local-only)
Persist configs via localStorage
Add themes/custom colors
Support multiple timers
Add progress bar
Add count-up mode
📜 License

Use it, modify it, break it. No one’s stopping you.
