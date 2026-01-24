# Copilot Instructions for K11 Software Solutions Website

## Project Overview
This repository is a static website for K11 Software Solutions, built with [Jekyll](https://jekyllrb.com/) and hosted on GitHub Pages. It features company information, a blog, portfolio/projects, and custom styles.

## Key Structure
- **Content Pages:** Markdown files at the root (about.md, services.md, portfolio.md, blog.md, contact.md, index.md)
- **Blog Posts:** `_posts/` (Markdown, Jekyll front matter)
- **Project Portfolio:** `_projects/` (Markdown, Jekyll front matter)
- **Custom Styles:** `assets/css/custom.css`
- **Includes:** `_includes/head.html` for head customization
- **Configuration:** `_config.yml` (site settings, navigation, plugins, collections)
- **Gems/Plugins:** `Gemfile` (jekyll-feed, jekyll-seo-tag, github-pages)

## Developer Workflows
- **Local Development:**
  - Install Ruby, Bundler, and run `bundle install`.
  - Start local server: `bundle exec jekyll serve` (serves at http://localhost:4000)
- **Build/Deploy:**
  - Deployment is automatic via GitHub Pages on push to `main`.
- **Add Blog Post:**
  - Add a Markdown file to `_posts/` with Jekyll front matter (see existing post for format).
- **Add Project:**
  - Add a Markdown file to `_projects/` with front matter (see example).
- **Custom CSS:**
  - Edit `assets/css/custom.css` for site-wide styles.

## Project-Specific Conventions
- **Navigation:** Controlled by `header_pages` in `_config.yml`.
- **Collections:**
  - `projects` and `team` are custom collections, output as pages.
- **Future Posts:** `future: true` in `_config.yml` allows scheduling posts ahead.
- **SEO & Feeds:** Managed by `jekyll-seo-tag` and `jekyll-feed` plugins.
- **No JavaScript Frameworks:** This repo is static; dynamic features require Jekyll plugins or custom JS (not present by default).

## Integration Points
- **GitHub Pages:** Automatic deployment.
- **Jekyll Plugins:** Managed via `Gemfile` and `_config.yml`.
- **Social Links:** Set in `_config.yml` for GitHub, Twitter, LinkedIn.

## Examples
- See `_posts/2026-01-22-welcome-to-our-blog.md` for blog post format.
- See `_projects/ecommerce-platform.md` for project format.
- See `_includes/head.html` for adding custom meta tags or CSS.

## References
- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)

---
If any conventions or workflows are unclear, please request clarification or examples from the repository maintainers.
