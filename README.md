# AEoN Lab website

Static site: 5 pages (Home, Research, Publications, People, Contact), one shared stylesheet, no build step, no dependencies.

## Deploy to GitHub Pages (free hosting)

1. Create a new GitHub repo, e.g. `AEoN-lab`.
2. Upload all files in this folder (`index.html`, `research.html`, `publications.html`, `people.html`, `contact.html`, the `css/` folder) to the repo root — either via the GitHub web UI ("Add file → Upload files") or:
   ```
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/AEoN-lab.git
   git push -u origin main
   ```
3. In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: main / (root)**. Save.
4. Your site goes live at `https://<your-username>.github.io/AEoN-lab/` within a minute or two.

## Custom domain (optional)

If you buy a domain (e.g. from Namecheap):
1. In the repo, add a file named `CNAME` containing just your domain, e.g. `AEoNlab.com`.
2. At your domain registrar, add a `CNAME` record pointing to `<your-username>.github.io`.
3. Back in GitHub Pages settings, enter the custom domain and enable "Enforce HTTPS."

## Editing content

Every page is a plain HTML file — open any of them in a text editor and edit the text directly; no templating system to worry about. All shared styling lives in `css/style.css`. To add a new publication, copy one `.pub` block in `publications.html` and edit the text.

## Adding your homepage photo

The homepage (`index.html`) now uses a full-bleed photo hero, styled after shmontgomery.co.uk. Right now it shows a placeholder pattern with a small "Photo pending" tag — to add a real photo:

1. Put your image in the `img/` folder, e.g. `img/hero.jpg` (a wide, landscape shot, ideally 1800px+ wide — insectary, fieldwork, or a specimen shot all work).
2. In `index.html`, find this line near the top:
   ```html
   <section class="photo-hero no-photo">
   ```
   and change it to:
   ```html
   <section class="photo-hero" style="background-image:url('img/hero.jpg');">
   ```
3. Remove or ignore the `<span class="hero-note">Photo pending...</span>` line once you're happy with it (it's just a visible reminder while the photo is missing).

The four small thumbnail tiles under the hero (Heliconius, Riodinids, stingless bees, insectary) work the same way — each has a `.frame` div with placeholder text; swap it for `<img src="img/your-photo.jpg" alt="...">` once you have real photos for each.

## What's real vs. placeholder

- Publications are real, pulled from Google Scholar / ORCID / journal records (DOIs link out and verified as of July 2026).
- The People page currently lists Francesco only, with a monogram placeholder in place of a portrait photo — swap in a real photo by replacing `<span class="monogram">FC</span>` in `people.html` with `<img src="img/your-photo.jpg" alt="Francesco Cicconardi">`, and drop the photo file into the `img/` folder.
- Email on the Contact page uses the Bristol address from public records — update if you'd prefer the USP address.
