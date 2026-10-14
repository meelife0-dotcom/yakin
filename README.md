# وِرد ورش (Wird Warsh)

Version 1 of the hifz recitation and revision tracker. Static site, no backend.
All data is stored in the user's browser (localStorage).

## Deploy: GitHub + Cloudflare Pages
1. Create a new GitHub repo and push these files:
   git init && git add . && git commit -m "v1"
   git branch -M main
   git remote add origin https://github.com/<you>/wird-warsh.git
   git push -u origin main
2. In the Cloudflare dashboard open Workers & Pages, create a Pages project, and connect it to the GitHub repo.
3. Framework preset: None. Build command: leave empty. Output directory: /
4. Save and deploy. You get a *.pages.dev address; add a custom domain later if you want one.
(Menu names in Cloudflare can change slightly; follow their Pages "Git integration" docs if so.)

## Known limits of v1
- Reminders only fire while the app is open. True background reminders need Web Push:
  a Cloudflare Worker with a Cron Trigger sending push messages, plus a small store of subscriptions.
- Data lives on one device. Accounts and sync need a backend (Cloudflare Workers + D1).
- No Quran text yet: add a verified Warsh text source (and its font) for the reader screen.
- Phase 2 (recitation scoring) needs a separate speech-to-text service.
