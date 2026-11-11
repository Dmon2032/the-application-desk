# The Application Desk

A Cosmic Filaments tool. Set your job search, prefill the answers every application asks for, keep resumes ready to attach, build or update a resume in the app, and stage each email for approval before anything goes out.

It is a single static page. No build step, no server, no accounts. Everything you type stays in your own browser.

## What's in this folder

| File | What it is |
| --- | --- |
| `index.html` | The whole app, including the splash page, banner, and the approved badge and artwork |
| `favicon.svg`, `favicon.ico`, `favicon-16.png`, `favicon-32.png`, `favicon-48.png` | Browser tab icons (a document with filament threads and a gold node, unique to this app) |
| `apple-touch-icon.png`, `icon-192.png`, `icon-512.png` | Home-screen and app icons |
| `site.webmanifest` | Lets phones add it to the home screen as "App Desk" |
| `netlify.toml` | Tells Netlify there is nothing to build, and adds security headers |
| `badge.png`, `scene.png` | The Cosmic Filaments badge and wide-format artwork, cropped from the brand book (already embedded in `index.html`; kept here for reuse) |

## Deploy, easiest way (about two minutes, no GitHub needed)

1. Unzip this folder.
2. Open https://app.netlify.com/drop
3. Drag the whole folder onto the page.
4. Netlify gives you a live link. Rename it under **Site configuration > Change site name**.

## Deploy with GitHub (so updates go live automatically)

1. On GitHub, click **New repository**. Name it `application-desk`. Leave it empty (no README, no license).
2. On the empty repo page click **uploading an existing file**. Drag in **everything inside** the unzipped folder (not the folder itself), then click **Commit changes**.
3. On Netlify click **Add new site > Import an existing project > GitHub** and choose `application-desk`.
4. Leave **Build command** empty. Set **Publish directory** to `.` (a single dot). Click **Deploy**.
5. From then on, every change you commit to GitHub deploys itself.

## Use your own address (optional)

In Netlify: **Domain management > Add a domain**. A subdomain such as `desk.cosmicfilaments.com` works well. Add the CNAME record Netlify shows you at your domain registrar.

## Check it after it goes live

- The splash page plays, and **Enter the desk** opens the app.
- The tab shows the document-and-filament icon, not a generic globe.
- Resumes tab: add a PDF, then use **Replace with newer file**. Build one in the builder, save it, then reopen it with **Edit in builder**.
- Applications tab: add a test job with your own email, tick the approval box, and open the Gmail draft.

## Things to know

- **Data lives in the visitor's browser** (localStorage) on that device and web address. It does not sync between devices. Use **Backup** to save a copy.
- **Resume files are stored in the browser**, up to about 3 MB each and roughly 4 MB total.
- **The app cannot attach files to an email or send email.** It opens a pre-filled draft. Attach the saved resume yourself, or export the approved queue from **Backup** and have Claude create Gmail drafts with the resume attached.
- **Passwords, Social Security numbers, and bank details are intentionally not collected.**
- The PDF maker loads `jsPDF 2.5.1` from cdnjs and the fonts (Archivo, Archivo Black) load from Google Fonts. Without internet the app still works; the builder shows a message and the type falls back to system fonts.
- If you change the fonts or scripts the page loads, update the `Content-Security-Policy` line in `netlify.toml` to match.

## Brand

Colors, type, voice, and artwork follow the Cosmic Filaments Brand Book, Volume One. The badge appears whole, on navy, and is never altered. The app banner reads THE APPLICATION DESK and uses the book's wide-format scene.

© Cosmic Filaments. All rights reserved.
