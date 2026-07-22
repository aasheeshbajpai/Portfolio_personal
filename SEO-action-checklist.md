# Making "Aasheesh Bajpai" return your portfolio on Google

Work top to bottom. Items marked **[you]** need your own login — I can't do those for you.

---

## Step 1 — Add the files to your repo (10 minutes)

1. Open your repo `aasheeshbajpai/Portfolio_personal` on GitHub.
2. Open `index.html`. Paste the contents of `seo-head-block.html` inside `<head>...</head>`.
   - Delete your **old** `<title>` and `<meta name="description">` so there are no duplicates.
   - Fill in the `<<< EDIT >>>` placeholders: your email, photo path, Scholar/ORCID/ResearchGate links.
   - Delete any `sameAs` line for a profile you don't actually have. A dead link there hurts you.
3. Upload `sitemap.xml` and `robots.txt` to the **root of the repo** (same folder as `index.html`).
4. Commit. Wait ~2 minutes for GitHub Pages to rebuild.
5. Verify both work in a browser:
   - `https://aasheeshbajpai.github.io/Portfolio_personal/sitemap.xml`
   - `https://aasheeshbajpai.github.io/Portfolio_personal/robots.txt`

> ⚠️ `robots.txt` only actually works at the *domain* root — on `github.io` the root belongs to GitHub, not you. It's harmless to include, but on `github.io` the sitemap submission in Step 3 is what actually matters. (On a custom domain, robots.txt works properly.)

---

## Step 2 — Fix the visible page content (10 minutes)

Google reads what a human sees, not just meta tags.

- [ ] Your **`<h1>`** must contain your full name. Not "Portfolio", not "Welcome", not "About Me".
      Good: `<h1>Aasheesh Bajpai</h1>` followed by `<h2>Ph.D. — Computational Fluid Dynamics, IIT Kanpur</h2>`
- [ ] Write your name in full at least 3–4 times naturally in the body text (in your bio paragraph, in the publications list as an author, in the footer). Don't stuff it — just don't write the whole page as "I".
- [ ] Add `alt` text to your profile photo: `alt="Aasheesh Bajpai"`.
- [ ] Add a plain-text footer line: `© 2026 Aasheesh Bajpai · Kanpur / Hyderabad, India`. Location text helps disambiguate you from other people with the same name.
- [ ] If you go by variants (Asheesh, Dr. Aasheesh Bajpai), work them into the page text once each.

---

## Step 3 — Google Search Console **[you]** (15 minutes — this is the highest-impact step)

1. Go to https://search.google.com/search-console
2. Click **Add property** → choose **URL prefix** (not Domain) → enter:
   `https://aasheeshbajpai.github.io/Portfolio_personal/`
3. Verification: choose the **HTML file** method. Google gives you a file like `google1a2b3c.html`.
   Upload it to your repo root, commit, then click Verify.
   - *If HTML file fails*, use the **HTML tag** method instead — paste the `<meta name="google-site-verification" ...>` tag into your `<head>` alongside the block from Step 1.
4. Left sidebar → **Sitemaps** → enter `sitemap.xml` → Submit.
5. Top search bar → paste your full URL → press Enter → click **Request Indexing**.

Then repeat the same idea at Bing (it feeds DuckDuckGo, Ecosia, and increasingly ChatGPT search):
https://www.bing.com/webmasters — it has a "Import from Google Search Console" button that does it in one click.

---

## Step 4 — Build the backlinks **[you]** (20 minutes, do all of them)

This is what actually makes Google connect the *name* to the *site*. One link is weak; six consistent ones are strong.

- [ ] **LinkedIn** → Edit profile → Contact info → Website → add URL, label it "Portfolio". Also add it to your **Featured** section as a link post.
- [ ] **LinkedIn post** — write one short post announcing the portfolio with the link. Public visibility. Real engagement = real crawl signal.
- [ ] **GitHub profile README** — create a repo named `aasheeshbajpai` (same as your username), add a `README.md` with your name as `# Aasheesh Bajpai` and a link to the portfolio. This appears on your GitHub profile page and GitHub has enormous domain authority.
- [ ] **GitHub repo settings** — on `Portfolio_personal`, click the ⚙️ next to "About" and set the Website field to your Pages URL, plus a description containing your name.
- [ ] **Google Scholar** → your profile → add homepage link.
- [ ] **ORCID** → Websites & social links section → add it. (If you don't have ORCID, make one — it's free, takes 5 min, and ORCID pages rank well.)
- [ ] **ResearchGate** → profile → add website.
- [ ] **IIT Kanpur lab/department page** — if your group lists members, email the webmaster and ask them to link your name to the portfolio. A `.ac.in` backlink is worth more than everything else on this list combined.
- [ ] Any conference/paper bio where you can list a URL.

**Consistency rule:** spell your name identically everywhere — "Aasheesh Bajpai". Mixed spellings split your search signal.

---

## Step 5 — Custom domain (optional but strongly recommended)

`aasheeshbajpai.github.io/Portfolio_personal/` is a *subfolder on a subdomain*. It will always be handicapped versus a real domain.

1. Buy `aasheeshbajpai.com` (~₹800–1000/year on Namecheap, Porkbun, or GoDaddy).
2. In your repo: Settings → Pages → Custom domain → enter it → Save. This auto-creates a `CNAME` file.
3. At your registrar, add DNS records:
   - Four `A` records for the apex `@`: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - One `CNAME` for `www` → `aasheeshbajpai.github.io`
4. Back in GitHub Pages settings, tick **Enforce HTTPS** (wait ~20 min for the certificate).
5. **Then** update every URL in `seo-head-block.html` and `sitemap.xml` to the new domain, and re-do Step 3 with the new property.

---

## Step 6 — Timeline and what to expect

| When | What |
|---|---|
| 1–3 days | Page appears in Google when you search the exact URL |
| 1–3 weeks | Appears for `"Aasheesh Bajpai" IIT Kanpur` or `Aasheesh Bajpai CFD` |
| 1–3 months | Appears on page 1 for plain `Aasheesh Bajpai` |

Check progress with: `site:aasheeshbajpai.github.io` in Google. If nothing shows after two weeks, go back to Search Console → **Pages** report and read the exclusion reason.

**Realistic expectation:** for the plain-name search, your LinkedIn will almost certainly outrank your portfolio for a long time — LinkedIn has vastly more authority. That's fine. The goal is for your portfolio to sit *next to* it in the top few results. Also note there are several other public figures named Bajpai (and at least one other Aasheesh); a custom domain plus the `knowsAbout` schema is what separates you from them.

---

## Step 7 — Keep it alive

Google ranks pages it sees changing. Once a month or so:
- Add a new publication, project, or talk
- Update the `<lastmod>` date in `sitemap.xml`
- Commit

Dormant sites slowly drift down. Ten minutes a month is enough to prevent that.
