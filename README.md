# Summarize — Chrome Extension

**Summarize any webpage instantly with AI. No sign-up required.**

Summarize turns long articles, blog posts, documentation, news, Reddit threads, X/Twitter posts, Gmail threads, and YouTube videos into clear, digestible summaries in seconds. Or simply ask a question about the page and get answers grounded in the content. Powered by [Claude AI](https://www.anthropic.com/) from Anthropic.

[Chrome Web Store link](https://chromewebstore.google.com/)

## Features

- **Free to use** — free with limits, no account needed. Upgrade to Pro for higher usage and to ask follow-up questions
- **One-click summaries** — click Summarize and get the key points instantly
- **Ask questions** — switch to Ask mode and ask anything about the page content
- **Reddit threads** — fetches post and comments directly from Reddit's API
- **Gmail threads** — get long email threads summarized with action items
- **YouTube videos** — extracts and summarizes the video transcript
- **X/Twitter** — summarize a single post with replies or your entire timeline
- **6 summary styles** — Concise, Detailed, Bullets, ELI5, Q&A, or One-Liner
- **Summarize selected text** — highlight a section and summarize just that part
- **Custom instructions** — tell the AI to focus on what matters to you ("focus on technical details" or "summarize in Spanish")
- **Summary history** — every summary is saved locally and searchable
- **Pin favorites** — pin important summaries to the top of your history
- **Full-page view** — expand any saved summary into a clean, full-page reading experience
- **Side panel mode** — keep Summarize open alongside your browsing
- **Dark mode** — toggle between light and dark themes
- **Keyboard shortcut** — press `Alt+S` to summarize without opening the popup
- **Word count & reading time** — see how long a page is before summarizing
- **Export & import data** — transfer your saved summaries between browsers (e.g. Chrome to Brave) via JSON file
- **Copy with one click** — copy any summary to your clipboard instantly

## How It Works

1. Navigate to any webpage, Reddit thread, YouTube video, Gmail, or X/Twitter post
2. Click the Summarize icon in your toolbar
3. Choose a summary style and click **"Summarize This Page"** — or switch to **Ask** mode, type a question, and click **"Ask About This Page"**
4. Read your summary or answer, copy it, ask a follow-up question, and find it later in History

<!--
## Installation

### From the Chrome Web Store

_(Coming soon)_


### From Source (Developer Mode)

1. Clone this repository:
   ```bash
   git clone https://github.com/hcote/summarizer.git
   ```
2. Open Chrome and navigate to `chrome://extensions`
3. Enable **Developer mode** (toggle in the top right)
4. Click **Load unpacked** and select the `extension/` folder


## Development

```bash
npm install          # Install dependencies
npm run dev          # Start Next.js dev server (localhost:3000)
npm run build        # Production build
```

When running locally, update `API_URL` in `extension/config.js` to `http://localhost:3000`.

To test Stripe webhooks locally:
```bash
stripe listen --forward-to localhost:3000/api/webhook
```
-->

## Privacy

- **No account required** — just install and start summarizing
- **100% private** — your summaries are saved locally in your browser, never stored on our servers

## Plans

|                         | Free        | Pro                   |
| ----------------------- | ----------- | --------------------- |
| Summaries & questions   | 10 lifetime | 50 per day            |
| Ask follow up quesions  | No          | Yes                   |
| All summary styles      | Yes         | Yes                   |
| Custom instructions     | Yes         | Yes                   |
| History & search        | Yes         | Yes                   |
| Subscription management | —           | Stripe billing portal |

Pro subscriptions are handled through [Stripe](https://stripe.com). You can manage or cancel your subscription anytime from the Account panel in the extension.

<!--
## Tech Stack

| Component          | Technology                                                |
| ------------------ | --------------------------------------------------------- |
| Extension          | Chrome MV3, Vanilla JS                                    |
| Content Extraction | Mozilla Readability.js, Reddit API, YouTube Innertube API |
| Backend            | Next.js App Router (TypeScript) on Vercel                  |
| AI Model           | Claude Haiku 4.5 (Anthropic)                              |
| Rate Limiting      | Upstash Redis                                             |
| Payments           | Stripe (Checkout, Billing Portal, Webhooks)               |

## Pack extension for submission

```bash
cd extension && zip -r ../summarize-extension.zip . -x ".\*"
```
-->

## Privacy Policy

https://docs.google.com/document/d/1H3VCPOwZva1iIDjEx-zPh3pKp71E1mr3JEHZ7Abnuns/edit?usp=sharing

## License

All rights reserved.
