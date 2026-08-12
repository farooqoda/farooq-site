# Muhammad Farooq Iqbal — website

Six pages. Each one is a single self-contained HTML file with its styling
inside it. No build step, no framework, no dependencies, nothing to install.

## See it

**Double-click `index.html`.** It opens in your browser and looks exactly as it
will when live. Works offline. Every page opens the same way.

## Put it online, free

**Cloudflare Pages** — commercial use permitted, no egress fees, free tier.

1. Push this folder to a GitHub repo
2. Cloudflare dashboard → Workers & Pages → Create → Pages → connect the repo
3. Build command: leave blank. Output directory: `/`
4. You get a live `*.pages.dev` URL in about two minutes — no domain needed

Adding a domain later: Custom domains → add → follow the DNS steps. No code changes.

Netlify and GitHub Pages work identically. Avoid Vercel — its Hobby plan
prohibits commercial use.

## Editing it

Open any `.html` file in a text editor. Change the words. Save. Refresh the browser.

The styling lives in a `<style>` block near the top of each file. It's identical
across all six, so if you change a colour, change it in all six — or move it back
out to a shared `style.css` once the site is hosted, where a shared file works fine.

Colours and fonts are CSS variables at the very top of the style block:

```css
--ink:#16233F;      /* text, dark sections */
--teal:#1F6E63;     /* buttons, links */
--signal:#E1591F;   /* the orange accent */
```

## Before it goes live

**1. Wire up the booking form.** In `book.html`, near the bottom:

```js
var ENDPOINT   = 'https://YOUR-N8N-HOST/webhook/web-chat';
var WIDGET_KEY = 'YOUR_WEB_WIDGET_KEY';
```

Get the key from your database:
```sql
SELECT name, web_widget_key FROM tenants;
```

Until those are set, the form shows a fallback message with your email and phone.
It fails usefully rather than silently.

**2. Get the privacy policy checked.** It's a plain-language starting point, not
lawyer-reviewed.

**3. Add a real screenshot.** The dashboard section on `systems.html` uses a small
sample table. A real screenshot of your follow-up log — with the "called off: no
SMS consent on record" row visible — is far more persuasive. Redact contact
details first.

## Pages

| File | Purpose |
|---|---|
| `index.html` | The promise, the problem, what it does, how it runs, what it won't do |
| `systems.html` | Both systems in depth, setup timeline, FAQ |
| `about.html` | The person, the track record, how you'd rather work |
| `work.html` | Advisory board campaign, the live system, what you learned |
| `book.html` | Four-field form with consent, wired to the orchestrator |
| `privacy.html` | Privacy policy and terms |
| `style.css` | Reference copy of the stylesheet (the pages don't need it — it's inlined) |

## On pricing

No figures appear anywhere on the site. The Systems FAQ explains the shape —
one-time setup plus a flat monthly, no per-call charges — and says the number
comes on the call. It anchors against a receptionist at $3,300–5,000/month so
the visitor has a sense of scale without being quoted.

## Design notes

The blueprint aesthetic — sheet numbers (`01 — The gap`), mono labels, hairline
rules, orange used once per screen — is carried from your existing portfolio.
Nothing else in this market looks like it. If you change one thing, don't change
this.

Accessibility: skip links, visible focus states, semantic headings, labelled form
fields, `prefers-reduced-motion` respected, AA contrast throughout.
