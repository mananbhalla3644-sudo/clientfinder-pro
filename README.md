# ClientFinder Pro

A client finder in one HTML file. No build, no install, no dependencies.

Open `clientfinder.html` in a browser and it works.

## What it does

You describe who you are and what you do. It scans a dozen-plus freelance and
job platforms, sorts what comes back against your profile, and gives you a
shortlist instead of a wall of links.

- **Profile** — your trade, skills and rate. Everything downstream keys off this.
- **Opportunities** — scan results, with filters you can reset in one click.
  Jobs can be starred and marked as applied.
- **Ready to Hunt** — the filtered shortlist.
- **Auto-Contact** — generate a personalised message per lead, then work
  through them.
- **Client List** — everything you have saved.

Message generation runs in two modes: **Parallel** sends every configured
provider at once and shows the results side by side, **Single** uses just your
primary one. Useful when you want to compare model output, or when you have
only one key.

Contacts and job state persist in `localStorage`, so closing the tab does not
lose your shortlist.

## Running it

Double-click the file. That is the whole install.

If your browser restricts `localStorage` or `fetch` on `file://` URLs, serve it
over HTTP instead:

```bash
npx serve .
# or
python -m http.server 8000
```

## A note on the APIs

This talks to job boards and to whatever AI provider you configure. Both kinds
of endpoint tend to rate-limit, change shape without notice, or ask for
credentials you would rather not paste into a page that keeps them in
`localStorage`. Two things follow from that:

- Treat any key you enter here as exposed to anyone with access to the browser
  profile. Use a key you can rotate and revoke cheaply.
- Nothing is sent anywhere until you press a button. There is no background
  polling.

## Requirements

A current desktop browser. The only network assets it loads are the Inter and
Sora web fonts from Google Fonts; everything else is inline, so it also works
offline once cached.

## Privacy

There is no analytics and no telemetry in this file. The only outbound requests
are the ones you trigger: the platform scans and the AI calls.
