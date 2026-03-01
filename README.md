# Townsite Urban Farm Website

Hugo static site for [townsiteuf.org](https://townsiteuf.org), hosted on Cloudflare Pages.

## Local Development

Requires [Hugo](https://gohugo.io/installation/) (Extended edition, v0.112+).

```bash
hugo server
```

Browse to http://localhost:1313. Changes hot-reload automatically.

## Writing a Blog Post

Create a new file in `content/blog/` named `YYYY-MM-DD-your-slug.md`:

```markdown
---
title: "Your Post Title"
date: 2026-03-15
description: "One sentence summary shown in listings and RSS."
author: "Your Name"   # optional
---

Post content goes here in Markdown.
```

Commit and push — Cloudflare Pages will build and deploy automatically.

## Updating the Reading List

Edit `data/books.yaml`. Each entry looks like:

```yaml
- title: "Book Title"
  author: "Author Name"
  url: "https://bookshop.org/..."    # optional but recommended
  description: "Why we love this book."
```

## Updating Partner Organizations

Edit `data/partners.yaml`. Each entry looks like:

```yaml
- name: "Organization Name"
  url: "https://example.org"         # optional
  description: "What they do."
```

## Cloudflare Pages Setup

1. In the [Cloudflare dashboard](https://dash.cloudflare.com), go to **Pages → Create application → Connect to Git**
2. Select the `townsite-urban-farm/website` repository
3. Set:
   - **Build command:** `hugo`
   - **Build output directory:** `public`
   - **Environment variable:** `HUGO_VERSION` = `0.157.0`
4. Click **Save and Deploy**
5. Once deployed, go to **Custom domains → Add custom domain** → enter `townsiteuf.org`
   - Cloudflare will auto-configure DNS since the domain is in the same account

## Subscribing to the RSS Feed

The blog RSS feed is available at: `https://townsiteuf.org/blog/index.xml`

Paste that URL into any feed reader (Feedly, NetNewsWire, etc.).
