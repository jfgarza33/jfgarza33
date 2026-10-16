# Paddle Raise Tracker

A single-page tool for recording a live paddle raise (fund-a-need) at a gala. A recorder taps the giving level the auctioneer calls, types each paddle number, and the running total updates on a big-screen view for the room.

No server, no accounts, no build step. It's one `index.html` file.

## What it does

- **Record:** Tap a giving level and enter paddle numbers, one at a time or several at once (`101 102 103`, separated by spaces, commas, or periods). Warns before recording the same paddle twice at one level. **Undo last** reverses the whole last entry, so a mistyped batch comes out in one tap.
- **Big screen:** Large running total, goal progress bar, and the paddles raised at the current level. Open it in a second window on the projector laptop; it stays in sync with the recording tab on the same browser.
- **Setup:** Event name, goal, lead gifts already pledged, an optional matching-gift cap, your giving levels, and an optional paddle-to-donor roster.
- **Export:** Download a CSV of every gift (time, paddle, donor name, level, amount) and copy a plain-text summary for the debrief email.

## Put it on GitHub

1. On github.com, tap **New repository**. Name it something like `paddle-raise-tracker`.
2. Choose **Public** or **Private** (see the data note below), then **Create repository**.
3. Tap **uploading an existing file** and add `index.html`, `README.md`, and `sample-roster.csv`. Commit to `main`.
4. To get a live link: **Settings → Pages → Build and deployment → Deploy from a branch → `main` / root → Save.** After a minute or two, your link appears at the top of that page, usually `https://YOUR-USERNAME.github.io/paddle-raise-tracker/`.

GitHub Pages is free on public repositories. Pages on a private repository requires a paid GitHub plan.

## Event-night workflow

1. **Before doors:** Open the live link on the recorder's device. Fill in Setup and paste the roster. Record two test paddles, check the big screen, then use **Clear all gifts**.
2. **Projector:** On the laptop connected to the screen, open the same link, go to **Big screen**, and tap **Full screen**. If one laptop does both jobs, use **Open in new window** for the projector and record in the other window.
3. **During the raise:** A spotter calls paddle numbers; the recorder enters them. Change the level as the auctioneer moves down.
4. **After:** Export the CSV and copy the summary before closing the browser.

## Data and privacy

- Gifts and the roster are saved in the browser's local storage on the device that entered them. Nothing is sent to GitHub or anywhere else.
- The repository holds only code, so a public repo exposes no donor data, as long as you never commit a real roster file. `sample-roster.csv` uses made-up names.
- Clearing the browser's site data, or using a private/incognito window, will erase recorded gifts. Export before you close.

## Limits to know before you rely on it

- **One recording device.** Sync works between tabs or windows on the same browser on the same computer. It does not sync a phone to a laptop. Two recorders on two devices means two separate tallies.
- **No audit trail beyond the CSV.** Treat the export, plus paper spotter sheets, as the record of gifts. Reconcile against pledge cards before acknowledgments go out.
- **Database import is manual.** Map the CSV columns to your donor database's import template and spot-check totals first.

## Ideas for a later version

- Multi-device sync (needs a small backend such as Firebase or Supabase, plus thought about donor data security)
- Per-paddle receipts or pledge-card printouts
- A DonorPerfect-ready column layout once the import template is confirmed

## License

Add a license of your choice before sharing the code publicly. MIT is a common, permissive option.
