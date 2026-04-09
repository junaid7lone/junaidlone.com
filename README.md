# systematica

> random hacks · systems thinking · code & chaos

Minimalist, centered, dark-mode-first blog for technical scribbles. PaperMod theme with cyberpunk neon accents. Built with [Hugo](https://gohugo.io/) + [Stack theme](https://github.com/CaiJimmy/hugo-theme-stack). Static = secure = fast.

## Quick Start

```bash
cd ~/blog

# Preview locally
hugo server --buildDrafts --disableFastRender

# Build production site
hugo --minify

# Create a new post
./newpost "Your Post Title" "category1,category2" "tag1,tag2"
```

The site runs at `http://localhost:1313` by default.

## Directory Structure

```
blog/
├── content/post/       → Your posts (markdown)
├── content/about.md    → About page
├── archetypes/         → Post frontmatter template
├── themes/PaperMod/       → Theme (git submodule)
├── hugo.toml           → Site configuration
├── assets/css/         → Custom CSS (overrides)
├── public/             → Generated site (commit this!)
└── newpost             → Post creation helper script
```

## Writing a Post

1. Run `./newpost "Title" "cat1,cat2" "tag1,tag2"` or copy `archetypes/default.md`
2. Edit the new file in `content/post/`
3. Use standard markdown, fenced code blocks, etc.
4. Add a `draft: false` frontmatter to publish
5. Test locally: `hugo server`
6. Commit and push

Frontmatter fields: `title`, `date`, `draft`, `categories[]`, `tags[]`, `image` (optional)

## Deployment (GitHub Pages)

1. Create a new repo on GitHub (e.g., `username.github.io` or `blog`)
2. Add remote: `git remote add origin git@github.com:USER/REPO.git`
3. Push: `git push -u origin main`
4. In GitHub repo settings → Pages → Source: Deploy from a branch → `gh-pages` (or main if using root)
5. Set baseURL in `hugo.toml` to `https://USER.github.io/` (or custom domain)

**Or use GitHub Actions** — create `.github/workflows/deploy.yml` to auto-deploy on push. (Let me know if you want that.)

## Customization

- **Colors**: edit `assets/css/custom.css` (cyberpunk neon palette pre-configured)
- **Site title, subtitle, menus**: edit `hugo.toml`
- **Avatars/favicons**: drop images into `static/` and reference in config
- **Disqus/analytics**: add under `[params.comments]` in config

## Security Notes

- Static site → no DB, no server-side execution, minimal attack surface
- Build runs locally; deploy only static files (`public/`)
- No tracking, no cookies, no external scripts by default

## Commands

```bash
# Build only
hugo --minify

# Clean build
rm -rf public && hugo --minify

# List all posts
hugo list posts

# New page (not post)
hugo new page/about.md
```

---

*Built with zero bloat. Commit the `public/` folder for deployment.*
