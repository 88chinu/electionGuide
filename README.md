# Election Guide Assistant

- A single-page, beginner-friendly web app that helps users understand election processes and voting basics across multiple countries.

- project link - [https://startling-trifle-8e9258.netlify.app](https://startling-trifle-8e9258.netlify.app/)

## Overview

`Election Guide Assistant` is a standalone HTML app with embedded CSS and JavaScript. It provides:

- Country-specific election guidance (India, United States, United Kingdom, Australia)
- Step-by-step election process timeline
- Voter eligibility checker
- Important election dates
- FAQ section
- AI-powered chat assistant (Anthropic API call from the browser)
- Optional voice input for chat (Web Speech API)
- Light/Dark mode toggle

Everything currently lives in one file:

- `election_guide_assistant.html`

## Features

- **Home Dashboard**
  - "At a glance" cards for election type, voting age, election body, and voting method
  - Important election date list per selected country
- **Process Timeline**
  - Clickable election stages (registration, nomination, campaigning, voting, counting, government formation)
- **Eligibility Checker**
  - Quick check based on age, citizenship status, and registration status
- **FAQ**
  - Common country-specific election questions
- **AI Chat Assistant**
  - Interactive Q&A experience for civic and election-related queries
  - Includes quick prompt suggestions
- **Voice Input**
  - Speech-to-text input for chat in supported browsers

## Tech Stack

- HTML5
- CSS3 (custom styles, responsive layout)
- Vanilla JavaScript (no framework/build step)
- Browser `fetch` API
- Web Speech API (`SpeechRecognition` / `webkitSpeechRecognition`)

## How to Run

No build or install steps are required.

1. Open `election_guide_assistant.html` directly in a modern browser.
2. Or serve it locally with any static server.

Example using Python:

```bash
python -m http.server 8080
```

Then open [http://localhost:8080/election_guide_assistant.html](http://localhost:8080/election_guide_assistant.html).

## AI Chat Integration Notes

The chat code sends requests to:

- `https://api.anthropic.com/v1/messages`

Current implementation is front-end only and does **not** include API authentication headers or a secure backend proxy. For production use:

- Add a backend endpoint that injects the Anthropic API key securely
- Never expose API keys in client-side JavaScript
- Add request validation/rate limiting on the backend

## Browser Compatibility

- Works best on latest Chrome/Edge/Firefox/Safari
- Voice input support is browser-dependent (best support in Chrome-based browsers)

## Project Structure

```text
.
├── election_guide_assistant.html
└── README.md
```

## Future Improvements

- Split HTML/CSS/JS into separate files
- Add secure backend service for AI chat
- Persist selected country and chat history in local storage
- Add localization (multi-language support)
- Add automated tests and linting

## Disclaimer

This project is educational and informational. Election rules and deadlines can change. Always verify final details on official election commission/government websites for the relevant country.

