# ythony's Personal Blog

A personal blog built with Jekyll 4.3, deployed to GitHub Pages with a custom domain (ythony.life).

## Project Structure

```
c-woojin.github.io/
├── _config.yml                 # Main Jekyll configuration
├── _layouts/                   # HTML templates
│   ├── default.html           # Base layout (header, footer, navigation)
│   ├── post.html              # Individual post layout
│   └── category.html          # Category page layout
├── _posts/                     # Blog posts (organized by year)
│   ├── 2025/
│   └── 2026/
├── assets/
│   ├── css/
│   │   └── style.css          # Main stylesheet (CSS variables, responsive)
│   └── images/
│       └── posts/             # Post images (organized by year/date-slug/)
│           ├── 2025/
│           └── 2026/
├── categories/                 # Category index pages
│   ├── books.md
│   ├── dev.md
│   └── life.md
├── about.md                    # About page
├── index.html                  # Home page (with pagination)
├── Gemfile                     # Ruby dependencies
├── Gemfile.lock               # Locked dependency versions
├── CNAME                       # Custom domain configuration (ythony.life)
└── CLAUDE.md                   # This file
```

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

Posts must follow the naming convention: `_posts/YYYY/YYYY-MM-DD-title.md`

**Front Matter Template:**
```yaml
---
layout: post
title: "Post Title"
date: YYYY-MM-DD HH:MM:SS +0900
categories: [category]
tags: [tag1, tag2]
---
```

**Available Categories:**
- `life` - Personal reflections, family, health, career
- `books` - Book reviews and reading insights
- `dev` - Development and technical topics

### Adding Images to Posts

Images should be organized by year and post date-slug:
```
assets/images/posts/YYYY/YYYY-MM-DD-slug/image-name.jpg
```

Reference in posts:
```markdown
![Alt text](/assets/images/posts/2026/2026-01-04-slug/image.jpg)
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

### Creating New Category Pages

Category pages go in `categories/` directory:

```yaml
---
layout: category
title: "Category Name"
category: category-slug
description: "Category description"
permalink: /categories/category-slug/
---
```

## Site Configuration

The site is configured in `_config.yml`:
- **Title**: ythony
- **Author**: ythony
- **Language**: Korean (ko)
- **Markdown**: kramdown
- **Permalink structure**: `/:year/:month/:day/:title/`
- **Pagination**: 10 posts per page
- **Custom Domain**: ythony.life (via CNAME)

### Analytics

Two analytics services are configured:
- **Google Analytics**: GA-4 (ID: G-933P53HPDC)
- **GoatCounter**: Visitor counter (code: cwoojin217)

## Active Plugins

- `jekyll-feed` (0.12): RSS feed generation
- `jekyll-seo-tag` (2.8): SEO meta tags
- `jekyll-paginate` (1.1): Post pagination

## Layout System

### default.html
Base layout with:
- Fixed header with dropdown navigation
- Container (max-width: 680px)
- Footer with copyright and visitor count
- Analytics scripts
- Favicon configurations

### post.html
Extends default with:
- Article title, date, categories
- Post content rendering
- Tags section
- Previous/next post navigation

### category.html
Extends default with:
- Category title and description
- Filtered post list by category
- Excerpts (30 words)

## CSS Architecture

The site uses a single stylesheet (`assets/css/style.css`) with:

**CSS Variables:**
```css
--color-bg: #fafafa
--color-text: #1a1a1a
--color-text-light: #666
--color-border: #e0e0e0
--color-accent: #000
--max-width: 680px
```

**Responsive Breakpoint:**
- Single breakpoint at `max-width: 768px`
- Fixed header requires `padding-top: 80px` (desktop) / `70px` (mobile)

## Important Notes

- **DO NOT** edit files in `_site/`, `.jekyll-cache/`, or `vendor/` - auto-generated
- **DO NOT** commit `Gemfile.lock` changes unless updating dependencies
- Posts are written in Markdown with YAML front matter
- All posts must have proper front matter to be processed
- The site uses kramdown for Markdown processing
- Local development runs on port 4000 by default
- Posts can be written in Korean or English

## Code Style

When modifying layouts or creating new posts:
- Use consistent indentation (2 spaces for YAML, HTML)
- Follow existing naming conventions
- Test locally before committing
- Keep post titles concise and descriptive
- Use appropriate categories and tags for organization

**Commit Message Convention:**
```
feat: Add new feature
fix: Fix a bug
chore: Maintenance tasks
refactor: Code refactoring
```

## Responsive Design

When modifying CSS or layouts:
- Always consider both desktop and mobile views
- The site uses a fixed header navigation - ensure `padding-top` is set in both base styles and responsive media queries to prevent content from being hidden behind the header
- Test responsive breakpoints (max-width: 768px) when making layout changes
- Navigation dropdown should remain accessible on mobile

## Deployment

- **Platform**: GitHub Pages
- **Repository**: c-woojin/c-woojin.github.io
- **Custom Domain**: ythony.life
- **Deploy Trigger**: Push to `main` branch automatically deploys
