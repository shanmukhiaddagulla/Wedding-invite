# Rashmitha & Uttej · Engagement Invitation

Single-file static site with live RSVP + comment wall (Firebase Realtime DB).

## 1. Add the photo
Save the couple photo you uploaded as **`couple.jpg`** in this folder (same level as `index.html`).
Recommended: ~1200px wide, JPG. The frame is responsive.

## 2. Paste Firebase config
Open `index.html`, find the block marked **`1) FIREBASE CONFIG`**, and replace the placeholder
values with the config from:
Firebase Console → Project settings → General → Your apps → Web app.

Make sure **Realtime Database** is created and the rules are in **test mode**:
```json
{ "rules": { ".read": true, ".write": true } }
```

## 3. Host free on GitHub Pages
```powershell
git init
git add .
git commit -m "Engagement invitation"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo>.git
git push -u origin main
```
Then in the repo: **Settings → Pages → Source: Deploy from branch → `main` / root → Save.**
Your site will be at `https://<your-username>.github.io/<repo>/`.

### Custom domain (optional)
In **Settings → Pages → Custom domain**, enter **only the bare host**:
- `yourdomain.com`  *(apex)*
- or `invite.yourdomain.com`  *(subdomain)*

Do **NOT** include `https://`, `http://`, or any trailing path.

## 4. Test locally
```powershell
# from this folder
python -m http.server 8080
# open http://localhost:8080
```

## Schema
```
rsvps/$id   → { name, attending: yes|no, guestCount: 1|2|3|4+, timestamp }
comments/$id → { name, message, timestamp }
```
