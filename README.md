# K11 Software Solutions Website

A professional business website built with Jekyll and hosted on GitHub Pages. This site showcases our software development services, portfolio, blog, and contact information.

## 🌐 Live Site

Visit us at: [https://k11softwaresolutions.com](https://k11softwaresolutions.com)

## 📋 Table of Contents

- [Project Overview](#project-overview)
- [Site Structure](#site-structure)
- [Navigation](#navigation)
- [Blog Feed & RSS](#blog-feed--rss)
- [Setup & Development](#setup--development)
- [Adding Content](#adding-content)
- [Deployment](#deployment)
- [Contact Form](#contact-form)
- [Contributing](#contributing)

## 🎯 Project Overview

This is a static website built with:
- **Jekyll** - Static site generator
- **Minima Theme** - Clean, responsive design
- **GitHub Pages** - Free hosting and deployment
- **Markdown** - Content authoring

### Key Features
- Professional service pages
- Dynamic blog with RSS feed
- Portfolio/project showcase
- Contact form integration
- SEO optimization with Jekyll SEO Tag
- Responsive design for all devices

## 📁 Site Structure

```
k11-software-solutions.github.io/
├── _config.yml              # Site configuration
├── _posts/                  # Blog posts
│   └── YYYY-MM-DD-title.md
├── _projects/               # Portfolio projects
├── _includes/               # Reusable components
├── _layouts/                # Page templates
├── assets/
│   └── css/
│       └── custom.css       # Custom styles
├── index.md                 # Homepage
├── services.md              # Services page
├── portfolio.md             # Portfolio page
├── blog.md                  # Blog index
├── about.md                 # About us page
├── contact.md               # Contact page
├── Gemfile                  # Ruby dependencies
└── README.md                # This file
```

## 🧭 Navigation

The website navigation is controlled by the `header_pages` setting in `_config.yml`:

```yaml
header_pages:
  - index.md        # Home
  - services.md     # Services
  - portfolio.md    # Portfolio
  - blog.md         # Blog
  - about.md        # About
  - contact.md      # Contact
```

### Navigation Structure
1. **Home** (`/`) - Landing page with company overview
2. **Services** (`/services/`) - Software development services
3. **Portfolio** (`/portfolio/`) - Showcase of completed projects
4. **Blog** (`/blog/`) - All blog posts with excerpts
5. **About** (`/about/`) - Company information and team
6. **Contact** (`/contact/`) - Contact form and information

## 📰 Blog Feed & RSS

### Dynamic Blog Rendering

The blog page (`blog.md`) automatically displays all blog posts dynamically using Jekyll's Liquid templating:

```liquid
{% for post in site.posts %}
  <!-- Post title, date, author, excerpt -->
{% endfor %}
```

Posts are rendered in reverse chronological order (newest first) with:
- Post title (linked to full article)
- Publication date
- Author name (if specified)
- Excerpt/preview
- "Read More" link

### RSS Feed

The site includes an **automatically generated RSS feed** for blog subscribers:

**Feed URL:** [https://k11softwaresolutions.com/feed.xml](https://k11softwaresolutions.com/feed.xml)

This feed is powered by the `jekyll-feed` plugin and includes:
- All published blog posts
- Full post content
- Publication dates
- Author information
- Post categories

#### Subscribe to Our Blog

Readers can subscribe using any RSS reader by adding the feed URL:
```
https://k11softwaresolutions.com/feed.xml
```

Popular RSS readers:
- Feedly
- Inoreader
- NewsBlur
- RSS readers built into browsers

### Blog Post Features

Each blog post supports:
- **Front Matter** - Metadata (title, date, author, categories)
- **Markdown Content** - Rich text formatting
- **Code Blocks** - Syntax highlighting
- **Images** - Embedded media
- **Links** - Internal and external references
- **Excerpts** - Automatic excerpt generation

## 🚀 Setup & Development

### Prerequisites

- Ruby 2.7 or higher
- RubyGems
- GCC and Make

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/K11-Software-Solutions/k11-software-solutions.github.io.git
   cd k11-software-solutions.github.io
   ```

2. **Install dependencies:**
   ```bash
   gem install bundler
   bundle install
   ```

3. **Run local development server:**
   ```bash
   bundle exec jekyll serve
   ```

4. **View the site:**
   Open [http://localhost:4000](http://localhost:4000) in your browser

### Development Commands

- **Build site:** `bundle exec jekyll build`
- **Serve with live reload:** `bundle exec jekyll serve --livereload`
- **Serve with drafts:** `bundle exec jekyll serve --drafts`
- **Clean build files:** `bundle exec jekyll clean`

## ✍️ Adding Content

### Adding a Blog Post

1. Create a new file in `_posts/` with the naming convention:
   ```
   YYYY-MM-DD-your-post-title.md
   ```

2. Add front matter at the top:
   ```yaml
   ---
   layout: post
   title: "Your Post Title"
   date: YYYY-MM-DD HH:MM:SS -0800
   author: Your Name
   categories: category1 category2
   ---
   ```

3. Write your content in Markdown below the front matter

4. Save the file and it will automatically appear on the blog page

**Example:**
```markdown
---
layout: post
title: "Getting Started with React"
date: YYYY-MM-DD HH:MM:SS -0800
author: K11 Team
categories: tutorial web-development
---

Your blog post content here...
```

### Adding a Portfolio Project

1. Create a new file in `_projects/` (e.g., `my-project.md`)

2. Add front matter:
   ```yaml
   ---
   layout: page
   title: Project Name
   description: Brief description
   technologies: [React, Node.js, AWS]
   ---
   ```

3. Add project details in Markdown

### Editing Pages

Edit any `.md` file in the root directory to update page content:
- `index.md` - Homepage
- `services.md` - Services
- `about.md` - About us
- `contact.md` - Contact information

## 🚢 Deployment

The site is automatically deployed via **GitHub Pages** when changes are pushed to the `main` branch.

### Deployment Process

1. Make changes and commit:
   ```bash
   git add .
   git commit -m "Your commit message"
   ```

2. Push to GitHub:
   ```bash
   git push origin main
   ```

3. GitHub Pages will automatically build and deploy (takes 1-2 minutes)

4. View your changes at: https://k11softwaresolutions.com

### Build Settings

Configuration is in `_config.yml`:
- **URL:** `https://k11softwaresolutions.com`
- **Theme:** Minima
- **Plugins:** jekyll-feed, jekyll-seo-tag

## 📧 Contact Form

The contact page includes an embedded Google Forms contact form for easy communication.

### Contact Form Features
- Name, Email, Subject, Message fields
- Spam protection via Google Forms
- Email notifications for form submissions
- Mobile-friendly design
- Matches website styling

### Setting Up Your Google Form

The site includes a placeholder form ID. To set up your actual Google Form:

1. **Create your Google Form** - Follow the detailed instructions in [CONTACT_FORM_SETUP.md](CONTACT_FORM_SETUP.md)
2. **Get the embed code** - Copy your form's embed URL from Google Forms
3. **Update contact.md** - Replace the placeholder form ID with your actual form ID
4. **Test** - Verify the form works on your local site before deploying

See [CONTACT_FORM_SETUP.md](CONTACT_FORM_SETUP.md) for complete step-by-step instructions on creating and configuring your Google Form.

### How It Works
1. Visitors fill out the form on `/contact/`
2. Submissions are sent to Google Forms
3. Form responses appear in the linked Google Sheet
4. Email notifications are sent to `k11softwaresolutions@gmail.com`

## 🤝 Contributing

We welcome contributions! To contribute:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Make your changes
4. Test locally with `bundle exec jekyll serve`
5. Commit your changes: `git commit -m "Add your feature"`
6. Push to your fork: `git push origin feature/your-feature`
7. Open a Pull Request

### Contribution Guidelines
- Follow existing code style and structure
- Test changes locally before submitting
- Write clear commit messages
- Update documentation as needed
- Keep changes focused and minimal

## 📝 License

Copyright © 2024-present K11 Software Solutions. All rights reserved.

## 📞 Contact

- **Email:** k11softwaresolutions@gmail.com
- **Website:** https://k11softwaresolutions.com
- **GitHub:** [@k11-software-solutions](https://github.com/k11-software-solutions)
- **LinkedIn:** [K11 Software Solutions](https://linkedin.com/company/k11-software-solutions)

---

**Built with ❤️ by K11 Software Solutions**