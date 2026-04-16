
---

# ⏱ Countdown Timer

A minimal, single-file countdown timer with a built-in link generator.
Configure a date, generate a URL, and use it anywhere.

---

## Overview

This project is a self-contained HTML file that serves two purposes:

* **Builder Mode**: Create a countdown by selecting a date and optional title
* **Countdown Mode**: Display a live countdown using URL parameters

No frameworks, no dependencies, no backend.

---

## Features

* Single HTML file (portable and lightweight)
* URL-based configuration (`?end=...`)
* Built-in countdown link generator
* Real-time updates (1-second interval)
* Automatic completion state ("Time’s Up")
* Responsive layout
* Clipboard copy support
* Works standalone or embedded

---

## How It Works

The app switches behavior based on the presence of the `end` parameter in the URL.

### Builder Mode

Triggered when no `end` parameter is present.

* Displays input fields for:

  * Event title (optional)
  * Target date and time
* Generates a shareable countdown URL
* Provides copy-to-clipboard functionality

### Countdown Mode

Triggered when `?end=` is present in the URL.

* Parses the target date
* Calculates remaining time
* Updates countdown every second
* Displays a completion message when time reaches zero

---

## URL Parameters

### Required

* `end`
  Format: `YYYY-MM-DDTHH:mm`
  Example:

  ```
  ?end=2026-01-01T00:00
  ```

### Optional

* `title`
  Example:

  ```
  ?end=2026-01-01T00:00&title=New%20Year
  ```

---

## Usage

### Run Locally

Open the HTML file directly in a browser.

### Deploy

Host the file on any static hosting platform:

* GitHub Pages
* Netlify
* Vercel

### Embed

```html
<iframe 
  src="https://yourdomain.com/index.html?end=2026-01-01T00:00" 
  width="100%" 
  height="300">
</iframe>
```

---

## Behavior Details

* Time is calculated using:

  ```
  remaining = endTime - currentTime
  ```
* Values are updated every second using `setInterval`
* Countdown stops automatically at zero
* Negative time is clamped to zero

---

## Error Handling

* Missing `end` → Builder Mode shown
* Invalid date → Error message displayed
* Past date → Countdown immediately completes

---

## Limitations

* Uses browser’s local timezone (no timezone normalization)
* Depends on system clock accuracy
* No persistent storage (settings are not saved)
* No support for seconds in input (limited by `datetime-local`)

---

## File Structure

```
index.html
```

All logic, styles, and UI are contained within a single file.

---

## Possible Improvements

* Add timezone support
* Store last configuration (localStorage)
* Custom themes and colors
* Progress indicator
* Count-up mode
* Multiple timers support

---

## License

Open for use and modification.

---
