# Rally Cut — install it on your phone

Rally Cut is a small web app. Put this folder on any free static host, open the link on your phone, and add it to your home screen. It then opens full-screen like a normal app. After the first visit it also works with no signal.

## 1. Put it online (pick one)

**GitHub Pages (free, permanent)**
1. Sign in at github.com with a personal account and create a new **public** repository, e.g. `rally-cut`.
2. Click **Add file → Upload files** and drag in everything in this folder (not the folder itself). Commit.
3. Go to **Settings → Pages**. Under "Build and deployment", choose **Deploy from a branch**, branch `main`, folder `/ (root)`, then **Save**.
4. After a minute or two your app is at `https://<your-username>.github.io/rally-cut/`.

**Netlify (free)**
1. Sign in at app.netlify.com and open **Sites → Add new site → Deploy manually**.
2. Drag this whole folder onto the page. You get a link like `https://something.netlify.app` (you can rename it in Site settings).

## 2. Install on your phone

- **iPhone:** open the link in **Safari**, tap **Share → Add to Home Screen**.
- **Android:** open the link in **Chrome**, tap **⋮ → Install app** (or Add to Home screen).

Open it once while you have internet so it saves itself for offline use.

## 3. Turn on the AI coach (optional)

The session report and highlight tools work with no account. The **Technique review** sends a few still frames of your strokes to Claude for coaching, which needs your own API key:

1. Create a key at console.anthropic.com (use a personal account and add a little credit, since each review costs a few cents).
2. In the app, open **Coach → AI coach setup** and paste the key.

The key is saved only on your phone and is sent only to Anthropic's API. Your videos never leave the phone; only the 3-frame stroke strips you see in the app are sent.

## Updating

Replace `index.html` with a new version, then change `VERSION` in `sw.js` (e.g. `rallycut-v3`) so phones pick up the update. Close and reopen the app twice to load it.

## Files

- `index.html` — the whole app
- `sw.js` — offline cache
- `manifest.webmanifest`, `icon-*.png`, `apple-touch-icon.png` — app name and icons
