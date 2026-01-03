# ythony's Personal Blog

This is a personal blog built with Jekyll 4.3.

## Project Structure

- `_posts/`: Blog posts in markdown format (YYYY-MM-DD-title.md)
- `_layouts/`: HTML templates (default.html, post.html)
- `_site/`: Generated static site (auto-generated, do not edit)
- `assets/`: Static assets (CSS, images, JavaScript)
- `_config.yml`: Site configuration
- `Gemfile`: Ruby dependencies

## Development Commands

```bash
# Install dependencies
bundle install

# Start local server (http://localhost:4000)
bundle exec jekyll serve

# Build site
bundle exec jekyll build

# Build with drafts
bundle exec jekyll serve --drafts
```

## Writing Guidelines

### Creating New Posts

Posts must follow the naming convention: `_posts/YYYY-MM-DD-title.md`

**Front Matter Template:**
```yaml
---
layout: post
title: "Post Title"
date: YYYY-MM-DD HH:MM:SS +0000
categories: [category1, category2]
tags: [tag1, tag2]
---
```

### Creating New Pages

Pages can be placed in the root directory with `.md` or `.html` extension.

**Front Matter Template:**
```yaml
---
layout: default
title: "Page Title"
permalink: /page-url/
---
```

## Site Configuration

The site is configured in `_config.yml`:
- Title: ythony
- Author: ythony
- Markdown: kramdown
- Permalink structure: /:year/:month/:day/:title/
- Pagination: 10 posts per page

## Active Plugins

- `jekyll-feed`: RSS feed generation
- `jekyll-seo-tag`: SEO meta tags
- `jekyll-paginate`: Post pagination

## Important Notes

- **DO NOT** edit files in `_site/`, `.jekyll-cache/`, or `vendor/` - these are auto-generated
- **DO NOT** commit `Gemfile.lock` changes unless updating dependencies
- Posts are written in Markdown with YAML front matter
- All posts must have proper front matter to be processed
- The site uses kramdown for Markdown processing
- Local development runs on port 4000 by default

## Code Style

When modifying layouts or creating new posts:
- Use consistent indentation (2 spaces for YAML, HTML)
- Follow existing naming conventions
- Test locally before committing
- Keep post titles concise and descriptive
- Use appropriate categories and tags for organization

## Responsive Design

When modifying CSS or layouts:
- Always consider both desktop and mobile views
- The site uses a fixed header navigation - ensure `padding-top` is set in both base styles and responsive media queries to prevent content from being hidden behind the header
- Test responsive breakpoints (max-width: 768px) when making layout changes

## Deployment

This blog appears to be a GitHub Pages site (c-woojin.github.io). Changes to the `main` branch will automatically deploy to GitHub Pages.
