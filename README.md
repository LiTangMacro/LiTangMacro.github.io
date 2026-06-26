# Li Tang — Personal Website

A fast, dependency-free personal academic website (plain HTML, CSS, and a little
JavaScript). It is designed to be hosted for free on **GitHub Pages**.

```
.
├── index.html              # All page content lives here
├── assets/
│   ├── css/styles.css      # All styling + light/dark theme tokens
│   ├── js/main.js          # Theme toggle, active-nav, footer year
│   ├── favicon.svg         # Browser tab icon (LT monogram)
│   └── img/                # Put profile.jpg here if you add a photo
├── .nojekyll               # Tells GitHub Pages to serve files as-is
└── README.md               # This file
```

No build step, no frameworks. Open `index.html` in a browser to preview locally.

---

## How to edit your content

Everything you'll normally change is in **`index.html`**, which is organised into
clearly commented sections:

- **Hero** — your name, title, affiliation, tagline, and the Email / Scholar / CV buttons.
- **About** — your bio and research-interest chips.
- **Research** — three lists: *Publications*, *Working Papers*, and *Politics and Business*.
- **CV** — link to your CV PDF.
- **Contact** — email, department, and online links.

### Add a new publication
Copy an existing `<li class="pub">…</li>` block and edit the title, authors, venue,
and year. Entries are plain text — no special formatting needed.

### Link a paper (PDF / DOI)
Wrap the title text in a link, e.g.:
```html
<p class="pub-title"><a href="https://doi.org/XXXX" target="_blank" rel="noopener">Paper title here</a></p>
```

### Add your photo
1. Drop a square image at `assets/img/profile.jpg`.
2. In `index.html`, find the `<div class="avatar">LT</div>` line in the Hero and
   replace it with:
   ```html
   <img class="avatar" src="assets/img/profile.jpg" alt="Li Tang" />
   ```

### Change the accent colour
In `assets/css/styles.css`, edit `--accent` (and `--accent-hover`) under both
`:root` (light theme) and `[data-theme="dark"]`.

---

## Deploy to GitHub Pages

You have two options. **Option A** gives you the clean URL `https://USERNAME.github.io`.

### Option A — User site (recommended)
1. Create a new GitHub repository named **exactly** `USERNAME.github.io`
   (replace `USERNAME` with your GitHub username, all lowercase).
2. Upload these files to the repo (drag-and-drop in the browser, or push with git — see below).
3. Go to **Settings → Pages**. Under *Build and deployment*, set
   **Source = Deploy from a branch**, **Branch = `main` / `(root)`**, then **Save**.
4. Wait ~1 minute, then visit **https://USERNAME.github.io**.

### Option B — Project site
1. Create a repo with any name, e.g. `website`.
2. Upload the files and enable Pages the same way (Settings → Pages → branch `main` / root).
3. Your site will be at **https://USERNAME.github.io/website/**.

### Pushing with git (instead of drag-and-drop)
From this folder:
```bash
git init
git add .
git commit -m "Initial personal website"
git branch -M main
git remote add origin https://github.com/USERNAME/USERNAME.github.io.git
git push -u origin main
```

---

## Custom domain (optional)
If you own a domain (e.g. `litang.com`):
1. Create a file named `CNAME` in this folder containing just your domain, e.g. `litang.com`.
2. In **Settings → Pages → Custom domain**, enter the same domain.
3. At your domain registrar, add the DNS records GitHub shows you (an `ALIAS`/`A`
   record for the apex domain, or a `CNAME` to `USERNAME.github.io` for a subdomain).

---

## Credits
Built as a static replacement for the original Google Sites page. Fonts: Inter (Google Fonts).
