# Dan Kiehl — personal site

A personal site built with [Hugo](https://gohugo.io), hosted free on GitHub Pages. It uses no external theme, so there's nothing to update.

## Writing a new article

1. Add a file to `content/articles/`, for example `content/articles/deemed-exports-101.md`.
2. Put this at the top:

   ```
   ---
   title: "Deemed exports 101"
   date: 2026-11-03
   draft: false
   description: "One-sentence summary shown in lists and link previews."
   topics: ["Export Controls"]
   ---
   ```

3. Write the rest in Markdown, then commit and push to `main`. The site rebuilds itself in about a minute.

You can do all of this in the GitHub website: open `content/articles`, choose **Add file → Create new file**, paste, then **Commit**. No local install is needed.

**Topic areas:** `topics` must use names from the `areas` list in `hugo.toml`: Export Controls, CUI & CMMC, FCL & Industrial Security, Infosec, or Privacy. An article can have more than one. Each area gets its own page under `/topics/`, and the Articles page has filter buttons. To rename or add an area, edit that list.

Projects work the same way in `content/projects/`. Use `stack: ["Tool", "Tool"]` in place of `topics`.

`draft: true` keeps a post off the live site.

## Email newsletter (Substack)

The site shows a "Get new posts by email" box on the homepage and under every article once you set it up.

1. Create a free Substack at substack.com, for example `danielkiehl.substack.com`.
2. In `hugo.toml`, set `substack = "danielkiehl"` (just the name, not the full address).
3. Commit. The Subscribe button now goes to your Substack signup page.

**When you publish a post:** in Substack, write a short email (2–4 sentences: the problem and the key point), and link to the full article on your site. Keep the full text on your site, not Substack, so search traffic builds on your own domain.

**If you move to Substack fully later:** your subscribers are already there. Put the newsletter on `newsletter.danielkiehl.com` and keep this site as your home page and archive, so old links keep working.

## Previewing locally (optional)

Install Hugo, then run `hugo server -D` and open http://localhost:1313. The `-D` flag shows drafts.

## One-time setup

1. Create a GitHub repo (public), and upload these files.
2. In the repo, go to **Settings → Pages → Source** and choose **GitHub Actions**.
3. Push to `main`. The site appears at `https://<username>.github.io/<repo>/`.
4. Custom domain: in **Settings → Pages → Custom domain**, enter your domain. At your registrar, add the DNS records GitHub shows you. Tick **Enforce HTTPS**.
5. Edit `hugo.toml` to set your LinkedIn URL, email, and `baseURL`.
