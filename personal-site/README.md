# Personal site

Minimal academic site. Static, built with [Zola](https://www.getzola.org) (one small
program, no Node/Ruby dependencies to rot), published free at `USERNAME.github.io` by
GitHub's own servers. No domain, no monthly cost, no terminal required.

You never install anything. You edit text files in the GitHub website; GitHub rebuilds
and republishes automatically on every save.

---

## Setup — entirely in your browser (no command line)

1. **Make a free GitHub account** at github.com.

2. **Create a repository named EXACTLY `USERNAME.github.io`** (your real username, all
   lowercase). Set it **Public**. Don't add a README.
   - This exact name is what makes the free URL `https://USERNAME.github.io` work.

3. **Upload the files.** On the empty repo page → "uploading an existing file" → drag in
   the **contents** of this folder (the `config.toml` file, the `content`, `templates`,
   `sass`, `static`, `.github` folders — NOT the outer folder itself). Commit.
   - Critical: `config.toml` must sit at the **top level** of the repo, not inside a
     subfolder. If the upload nests everything one level down, the build finds nothing.

4. **Set `base_url`.** Click `config.toml` → pencil (Edit) → change the `base_url` line to
   `https://USERNAME.github.io` → "Commit changes". (Edit `title` and `author` while
   you're here, or later.)

5. **Turn on Pages.** Repo → **Settings** → **Pages** → *Build and deployment* → Source:
   **GitHub Actions**.

6. **Confirm it built.** Go to the **Actions** tab. A run appears for your last commit.
   - Green check → open `https://USERNAME.github.io`. It's live.
   - Red X → click the run, copy the error text, send it to me. I'll tell you the fix.

That's the entire deployment. Steps 3–6 take ~10 minutes.

---

## Writing (also entirely in the browser)

Every change is the same loop: edit a file on github.com → "Commit changes" → wait ~1 min →
refresh your site.

- **New note:** in `content/blog/`, "Add file → Create new file", name it `my-slug.md`:
  ```
  +++
  title = "Title"
  date = 2026-07-01
  +++
  Your text in Markdown.
  ```
- **Margin note** (the signature device), inline anywhere in the text:
  - Numbered: `... a claim{{ sidenote(text="the caveat goes here") }}.`
  - Unnumbered: `...{{ marginnote(text="an aside") }}`
- **CV PDF:** upload `cv.pdf` into the `static/` folder; it's already linked from the CV page.

Markdown basics: `# Heading`, `**bold**`, `*italic*`, `[link](https://...)`, `- bullet`.
That's nearly all you'll use.

---

## If something breaks

The build runs on GitHub and reports pass/fail on the **Actions** tab. A red X never
touches your live site (the previous version stays up). Copy the error, send it over.

Most likely first failure: an invalid syntax-highlight `theme` name in `config.toml`
under `[markdown]`. Everything else is already wired.

## Deliberately omitted

No analytics, cookies, trackers, web fonts, JavaScript framework, comments, or paid
domain. These are choices to add later, never defaults — and the free URL is permanent.

## Optional, only once you're comfortable (ignore for now)

- Local preview with live reload: install Zola, run `zola serve`.
- Faster editing via `git` on your computer instead of the website.
- Math (LaTeX): uncomment the KaTeX block in `templates/partials/head.html`.
