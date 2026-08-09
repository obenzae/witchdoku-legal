# Witchdoku legal pages

Static Terms of Service and Privacy Policy for the in-app Settings links.

| File | URL path after hosting |
|------|------------------------|
| `tos.html` | `/tos.html` |
| `privacy.html` | `/privacy.html` |
| `pp.html` | `/pp.html` (same as privacy; used by the game) |

**Before publishing:** replace placeholder emails in the HTML files:

- `support@honestygames.com`
- `privacy@honestygames.com`

---

## Option A — GitHub Pages (free, recommended)

1. Create a GitHub account if you do not have one.
2. Create a new repository, e.g. `witchdoku-legal`.
3. Upload everything in this `legal/` folder to the repo root (`tos.html`, `privacy.html`, `pp.html`, `styles.css`).
4. On GitHub: **Settings → Pages → Build and deployment → Source: Deploy from branch → Branch: `main` / `/ (root)` → Save**.
5. After 1–2 minutes your site is live at:
   ```
   https://obenzae.github.io/witchdoku-legal/tos.html
   https://obenzae.github.io/witchdoku-legal/privacy.html
   ```
6. Update the game URLs (see below) to those addresses.
7. For App Store Connect, paste the same URLs in **App Privacy** and **App Information** fields that ask for Privacy Policy URL.

### Quick upload from your Mac

```bash
cd /Users/oussama/Meogame/legal
git init
git add tos.html privacy.html pp.html styles.css
git commit -m "Add Witchdoku legal pages"
git branch -M main
git remote add origin https://github.com/obenzae/witchdoku-legal.git
git push -u origin main
```

---

## Option B — Cloudflare Pages (free, custom domain)

1. Sign up at [cloudflare.com](https://www.cloudflare.com).
2. **Workers & Pages → Create → Pages → Upload assets**.
3. Drag the `legal/` folder contents into the upload area.
4. Deploy. You get a URL like `https://witchdoku-legal.pages.dev/tos.html`.
5. Optional: add your own domain under **Custom domains**.

---

## Option C — Netlify (free)

1. Sign up at [netlify.com](https://www.netlify.com).
2. **Add new site → Deploy manually** and drop the `legal/` folder.
3. Use the generated URL, e.g. `https://random-name.netlify.app/tos.html`.

---

## Point the game to your URLs

After hosting, edit these two files and replace the URLs with yours:

- `godot-recovered/scripts/module/setting/view/setting_page.gd` (Terms + Privacy buttons)
- `godot-recovered/scripts/module/splash/view/privacy_dialog.gd` (first-launch dialog)

Default placeholders in the project:

```
https://obenzae.github.io/witchdoku-legal/tos.html
https://obenzae.github.io/witchdoku-legal/pp.html
```

Then re-export iOS and reinstall the app.

---

## App Store checklist

- [ ] Privacy Policy URL is publicly reachable (no login required)
- [ ] Terms URL opens in Safari from the app Settings screen
- [ ] URLs use `https://` (required by Apple)
- [ ] Contact email in the pages is a real inbox you monitor

---

## Local preview

Open the files in a browser:

```bash
open /Users/oussama/Meogame/legal/tos.html
open /Users/oussama/Meogame/legal/privacy.html
```

Or run a tiny local server:

```bash
cd /Users/oussama/Meogame/legal && python3 -m http.server 8080
```

Then visit `http://localhost:8080/tos.html`.
