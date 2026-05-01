[README.md](https://github.com/user-attachments/files/27271463/README.md)
# ⚡ CodeAI — Code Explainer + Debug Helper

A dark-themed, browser-based AI tool that explains, debugs, and improves your code — powered by Claude Sonnet via the Anthropic API. No server, no build step, no dependencies. Just open and use.

---

## Features

- **Explain** — plain-English breakdown of what the code does, how it works, and what patterns it uses
- **Debug** — identifies bugs and warnings with exact fixes and code examples
- **Improve** — ranked suggestions for performance, readability, error handling, and best practices
- **Complexity** — Big-O time and space analysis with optimized alternatives
- **Language selector** — JavaScript, TypeScript, Python, Java, C++, Go, Rust, SQL, Bash, or auto-detect
- **Split-panel layout** — code input on the left, live results on the right
- **Copy output** — one-click copy of the full analysis
- **Keyboard shortcut** — `Cmd+Enter` / `Ctrl+Enter` to run analysis instantly

---

## Getting Started

### 1. Get an Anthropic API Key

Sign up at [console.anthropic.com](https://console.anthropic.com) and create an API key.

### 2. Open the File

No installation needed. Just open `code-explainer.html` in any modern browser (Chrome, Firefox, Safari, Edge).

```bash
open code-explainer.html        # macOS
start code-explainer.html       # Windows
xdg-open code-explainer.html   # Linux
```

### 3. Use the App

1. Paste any code snippet into the left panel
2. Select a language (or leave on Auto)
3. Choose an analysis mode — Explain, Debug, Improve, or Complexity
4. Click **Analyze** or press `Cmd/Ctrl + Enter`
5. Results appear in the right panel

---

## API Key Setup

The app calls the Anthropic API directly from the browser. To keep your API key secure, consider one of the following:

**Option A — Environment variable via a local proxy (recommended for teams)**
Run a lightweight local proxy (e.g. with Express or Flask) that injects the key server-side, and point the fetch URL to `http://localhost:PORT/v1/messages`.

**Option B — Hardcode for personal use only**
In `code-explainer.html`, find the `fetch` call and add your key to the headers:

```js
headers: {
  'Content-Type': 'application/json',
  'x-api-key': 'YOUR_API_KEY_HERE',
  'anthropic-version': '2023-06-01'
}
```

> Never commit an API key to a public repository.

---

## File Structure

```
code-explainer.html   # The entire app — HTML, CSS, and JS in one file
README.md             # This file
```

---

## Model

Uses **claude-sonnet-4-20250514** with `max_tokens: 1000`. To change the model or increase output length, edit these lines in the `runAnalysis()` function:

```js
model: 'claude-sonnet-4-20250514',
max_tokens: 1000,
```

---

## Supported Languages

| Language | Auto-detected |
|---|---|
| JavaScript / TypeScript | Yes |
| Python | Yes |
| Java | Yes |
| C++ | Yes |
| Go | Yes |
| Rust | Yes |
| SQL | Yes |
| Shell / Bash | Yes |

---

## Browser Compatibility

| Browser | Support |
|---|---|
| Chrome 90+ | Full |
| Firefox 88+ | Full |
| Safari 14+ | Full |
| Edge 90+ | Full |

---

## License

MIT — free to use, modify, and distribute.

---

## Credits

Built with the [Anthropic Messages API](https://docs.anthropic.com/en/api/messages). Fonts: [JetBrains Mono](https://www.jetbrains.com/legalnotices/font/) and [Syne](https://fonts.google.com/specimen/Syne) via Google Fonts.
