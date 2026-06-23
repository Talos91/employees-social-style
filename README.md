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

## Team board (shared results)

The result page has an **"➕ Add me to the team board"** button. Everyone who opts in is plotted
as a colored dot (by style) with their name on a shared 2×2 grid — great for a team workshop.

**Out of the box it runs in local demo mode** (sample dots, saved only in that browser). To make
the board real and shared across everyone, connect a free Firebase project — ~5 minutes, one time:

1. Go to <https://console.firebase.google.com> → **Add project** (e.g. `social-style-board`).
   Google Analytics can be off.
2. In the project, click the **Web** icon `</>` → register an app → copy the `firebaseConfig` object.
3. **Build → Firestore Database → Create database** → production mode → location `asia-southeast1`.
4. Firestore **→ Rules** tab → paste the rules below → **Publish**:

   ```
   rules_version = '2';
   service cloud.firestore {
     match /databases/{database}/documents {
       match /results/{doc} {
         allow read: if true;
         allow create: if request.resource.data.name is string
                       && request.resource.data.name.size() > 0
                       && request.resource.data.name.size() < 60
                       && request.resource.data.style is string
                       && request.resource.data.a is number
                       && request.resource.data.r is number;
         allow update, delete: if false;
       }
     }
   }
   ```

5. Paste the config values into `FIREBASE_CONFIG` near the top of the `<script>` in `index.html`
   (`apiKey`, `authDomain`, `projectId`, `appId`), then commit + push. The board goes live and
   updates in real time as people finish.

Notes:
- The Firebase web config is **not** a secret — it's meant to live in client code, safe to commit.
- These rules let anyone with the link **read** the board (fine for an internal team tool) and
  **create** a result, but never edit/delete. Lock down further later if needed.
- Retakes just add a new entry; the board shows the latest result per name.

## How it scores

- 10 paired statements, each rated 1–8.
- 5 items measure **Assertiveness** (asks ↔ tells), 5 measure **Responsiveness** (controls ↔ shows emotion).
- Each axis is averaged; the midpoint (4.5) splits the 2×2 grid into the four styles.

## Editing

It's one file. Open `index.html`, edit, commit, and push to `main` — GitHub Pages redeploys
automatically within a minute or so.
