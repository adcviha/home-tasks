---
name: pillar-notes
description: Pillar Notes deployment rules — always push to GitHub Pages after changes.
metadata:
  type: project
---

# Pillar Notes

## CRITICAL: always deploy after changes

Every revision to this project MUST be pushed to `main` on GitHub. GitHub Pages serves
the live app from the `main` branch at `https://adcviha.github.io/pillar_notes/`.

After any code change:
```bash
cd /home/adc_viha/pillar_notes
git add -A
git commit -m "describe the change"
git push origin main
```

The site is live within ~30 seconds of pushing.

## Architecture

- Single HTML file (`index.html`) — vanilla JS, no build step
- Firebase Realtime Database for storage and real-time sync
- Shared passphrase (SHA-256 hashed) for access control
- Database URL: `https://pillar-notes-default-rtdb.firebaseio.com`
- Firebase project: `pillar-notes` (adcviha Google account)

## Data

- Tasks stored in Firebase at `/tasks/{taskId}`
- Passphrase hash at `/config/passhash`
- Legacy backup: `tasks.json.backup`
