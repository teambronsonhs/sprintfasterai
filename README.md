# Sprint Faster AI — content site

A static, multi-page SEO content hub for sprintfasterai.com: a homepage, an about page, and six cornerstone training articles, all linking through to the Sprint Faster AI app. Plain HTML/CSS, no build step, ready for GitHub Pages.

## What's assumed

You only confirmed GitHub for hosting, so two things were decided for you and are easy to change:
- **Content focus:** a mix of sprint topics (technique, gym strength, nutrition, sleep/recovery, beginner plans, youth training) to cover the widest spread of search terms.
- **Starting volume:** 6 cornerstone articles. More can be added any time using the same template — just ask.

## File structure

```
index.html              Homepage
about.html               About Bronson Hearn-Smith
blog/index.html           Article hub
blog/*.html               The 6 articles
css/styles.css            Shared design system
CNAME                     Custom domain for GitHub Pages
robots.txt, sitemap.xml   Basic SEO files
```

## Deploy to GitHub Pages

1. **Create a new repository** on GitHub (public, so Pages can serve it on the free tier) — e.g. `sprintfasterai-site`.
2. **Upload these files** to the repo root, keeping the folder structure intact (the `css/` and `blog/` folders need to stay where they are). Easiest way: drag the unzipped contents into the GitHub web UI's "Add file → Upload files," or `git add . && git commit -m "Initial site" && git push` if you're comfortable with git.
3. In the repo, go to **Settings → Pages**.
4. Under **Build and deployment**, set Source to **Deploy from a branch**, branch **main**, folder **/ (root)**. Save.
5. Still in **Settings → Pages**, under **Custom domain**, enter `sprintfasterai.com` and save. GitHub will detect the `CNAME` file already in the repo and should auto-fill this, but it's worth double-checking it saved correctly.

## Point your domain at GitHub Pages

At your domain registrar (wherever you bought sprintfasterai.com), update DNS:

- **Apex domain (sprintfasterai.com):** add four **A records** pointing to GitHub's IPs:
  - 185.199.108.153
  - 185.199.109.153
  - 185.199.110.153
  - 185.199.111.153
- **www subdomain (optional but recommended):** add a **CNAME record** for `www` pointing to `yourgithubusername.github.io`.

DNS changes can take anywhere from a few minutes to ~24 hours to propagate. Once it has, back in **Settings → Pages**, tick **Enforce HTTPS** — GitHub issues a free certificate automatically once it verifies the domain.

## After it's live

- Submit `sprintfasterai.com/sitemap.xml` in Google Search Console to speed up indexing.
- Every article links to the app at `https://studio.com/apps/bronson/sprintfasterai` — update that URL everywhere (a simple find-and-replace across the `.html` files) if the app's address ever changes.
- To add a new article: copy any file in `blog/`, swap the content, and add it to `blog/index.html`, the homepage card grid, and `sitemap.xml`.
