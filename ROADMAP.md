# Roadmap

Ideas, roughly in priority order. Nothing here is committed — pick what's useful.

## Result collection (biggest gap)
Right now results only come back if the employee clicks "Email my result back" (mailto), which
fails on webmail without a configured mail client. Options to auto-collect:
- **Google Form / Sheet**: simplest, no code. Mirror the result into a hidden form submit, or
  just add a "submit to HR" step that POSTs to a Google Apps Script web app → Sheet.
- **Serverless endpoint** (Cloudflare Worker / Firebase Function) writing to a sheet or DB.
- A team dashboard showing everyone's styles on one grid (great for a workshop).

## Content / accuracy
- Let employees nudge their dot if self-perception differs ("does this feel right?").
- Add the optional "how others see me" version (peer-rated) for a fuller Social Styles picture.
- Short "adapt to other styles" cheat-sheet on the result page (versatility is the real point).

## Polish / distribution
- Custom domain (e.g. style.internsinasia.com) instead of the github.io URL.
- Company logo + colors in the header.
- Translations (Thai) if sending to the Bangkok team.
- Per-employee shareable result link (encode answers in the URL hash).
