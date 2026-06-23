# Employees — Social Style self-assessment

A short (2-minute) self-assessment that maps how someone comes across at work onto the
**Social Styles** model (David Merrill & Roger Reid): **Analytical, Driving, Amiable, Expressive**.

Built as a single self-contained `index.html` — no build step, no backend.

## Live link

👉 **https://talos91.github.io/employees-social-style/**

Send that link to employees. They answer 10 questions and get their style plus practical
"how to work with me" tips. Nothing is stored on a server.

## How results come back to you

The result page has an **"✉ Email my result back"** button that opens the employee's mail
client pre-filled to the address set in `index.html`. There's also a **Copy summary** button
and **Save as PDF**.

To change the destination email, edit this line near the top of the `<script>` in `index.html`:

```js
var SEND_RESULTS_TO = "daniele@internsinasia.com";
```

## How it scores

- 10 paired statements, each rated 1–8.
- 5 items measure **Assertiveness** (asks ↔ tells), 5 measure **Responsiveness** (controls ↔ shows emotion).
- Each axis is averaged; the midpoint (4.5) splits the 2×2 grid into the four styles.

## Editing

It's one file. Open `index.html`, edit, commit, and push to `main` — GitHub Pages redeploys
automatically within a minute or so.
