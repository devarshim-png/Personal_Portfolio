# Personal portfolio (GitHub Pages)

Static site: portfolio home + printable résumé.

## Preview locally

From the repo root:

```bash
python3 -m http.server 8080 --directory docs
```

Open [http://localhost:8080](http://localhost:8080).

## Publish on GitHub Pages

### Option A — This repository

1. Push the repo to GitHub.
2. **Settings → Pages → Build and deployment**
   - Source: **GitHub Actions** (workflow in `.github/workflows/pages.yml`), **or**
   - Source: **Deploy from a branch**, folder **`/docs`**, branch **`main`**.
3. After deploy, the site URL is  
   `https://<username>.github.io/<repo-name>/`  
   (for a repo named `recruitment-screening-assessment`, paths in HTML assume that base).

### Option B — User site (`username.github.io`)

1. Create a repo named **`yourusername.github.io`**.
2. Copy the contents of **`docs/`** into the **root** of that repo (not inside `docs/`).
3. Enable Pages from the **`main`** branch, root **`/`**.
4. Your site will be **`https://yourusername.github.io`**.

## Customize

| File | What to edit |
|------|----------------|
| `index.html` | Headline, projects, contact links |
| `resume.html` | Experience, education, skills |
| `css/style.css` | Colors and layout tokens in `:root` |

Replace placeholder email, LinkedIn, GitHub URLs, and the three sample projects marked *Replace with your project*.

For project links to work on GitHub Pages, use full URLs to GitHub raw or repo paths (relative links like `../system-design.md` work in the repo browser but not always on Pages unless you add that file under `docs/`).
