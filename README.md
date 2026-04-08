# Summarize — AI Page Summaries

One-click AI summaries for any webpage. Ask follow-up questions about page content. No signup required.

[Add to Chrome](https://chromewebstore.google.com/detail/Summarize/ekociagdlamdenigjpmkobcnicmabcoo) | [Website](https://summarizeai.xyz)

---

## What It Does

Summarize is a Chrome extension that uses AI to instantly turn any webpage into a concise summary. Users can also questions about the page or have a multi-turn conversation — like having a research assistant built into your browser.

**Key features:**

- **One-click summaries** — Click the extension icon or press `Alt+S` to summarize any page
- **Ask questions** — Ask specific questions about the page content and get instant answers
- **Multi-turn chat** — Have back-and-forth conversations with AI about what you're reading
- **Multiple summary styles** — Choose the format that works best for you
- **Platform-aware** — Specialized extraction for YouTube transcripts, Reddit threads, X/Twitter threads, Gmail emails, and more
- **History** — Saved summaries are auto-restored when you revisit a page
- **Light & dark themes** — Matches your preference
- **Side panel support** — Use as a popup or pin it as a side panel
- **No account needed** — Start using it immediately with 15 free requests

## Supported Platforms

| Platform                      | What Gets Summarized                          |
| ----------------------------- | --------------------------------------------- |
| **Any webpage**               | Article body via Readability.js               |
| **YouTube**                   | Video transcript (via Innertube API)          |
| **Reddit**                    | Post + top comments (via old.reddit.com JSON) |
| **X / Twitter**               | Tweet thread content                          |
| **Gmail**                     | Email thread (sender, date, body)             |
| **Wikipedia**                 | Article content (references/links stripped)   |
| **Medium, NYT, Notion, etc.** | Article content like any standard page        |

## How It Works

1. **Visit any page** — Open something you want to understand quickly
2. **Click Summarize** — The extension extracts page content and sends it to the API
3. **Read or ask** — Get a summary, ask a question, or start a conversation

Responses stream in real-time so you can start reading immediately.

## Architecture

**Chrome Extension** → **Next.js API (Vercel)** → **Anthropic Claude API**

```
┌──────────────────┐     ┌──────────────────┐     ┌──────────────┐
│ Chrome Extension │────▶│  Next.js API     │────▶│  Claude API  │
│ (MV3, vanilla JS)│◀────│  (Vercel)        │◀────│  (Anthropic) │
└──────────────────┘ SSE └──────────────────┘     └──────────────┘
                              │
                              ▼
                        Upstash Redis
                    (rate limiting, metrics)
```

- **Extension** (`extension/`) — Popup UI, content extraction scripts, and a background service worker
- **API** (`src/app/api/`) — Next.js Route Handlers that validate input, enforce rate limits, and stream Claude responses via SSE
- **Frontend** (`src/app/`) — Landing page, privacy policy, admin dashboard, and Stripe callback pages served by Next.js App Router
- **Shared lib** (`src/lib/`) — CORS, rate limiting, validation, metrics, Sentry error tracking, and streaming helpers

### Tech Stack

| Layer      | Technology                          |
| ---------- | ----------------------------------- |
| Extension  | Vanilla JS, Chrome MV3 APIs         |
| API        | Next.js, TypeScript, Vercel         |
| AI         | Anthropic Claude (claude-haiku-4-5) |
| Database   | Upstash Redis                       |
| Payments   | Stripe (Checkout + Billing Portal)  |
| Monitoring | Sentry, Redis-backed analytics      |
| Testing    | Vitest                              |

## Pricing

|               | Free           | Pro          |
| ------------- | -------------- | ------------ |
| Summaries     | 15 per 90 days | 50/day       |
| Ask & Chat    | 15 per 90 days | 50/day       |
| Max page size | 3,000 words    | 10,000 words |

Summaries, questions, and chat messages all share the same quota.

## Privacy

No account or login required. Rate limiting is IP-based for free users and license-based for Pro. Page content is sent to the API for summarization but is not stored. See the full [Privacy Policy](https://summarizeai.xyz/privacy).

## License

This project is proprietary. All rights reserved.

## Feedback or Feature Requests

File an issue!
