---
layout: page
title: Portfolio
permalink: /portfolio/
---

Explore our recent projects and see how we've helped businesses transform their ideas into successful software solutions.

<div class="portfolio-grid">
  {% for project in site.projects %}
    <div class="portfolio-item">
      <h3><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h3>
      <p class="project-description">{{ project.excerpt }}</p>
      {% if project.technologies %}
        <div class="tech-tags">
          {% for tech in project.technologies %}
            <span class="tech-tag">{{ tech }}</span>
          {% endfor %}
        </div>
      {% endif %}
      <a href="{{ project.url | relative_url }}" class="view-project">View Project →</a>
    </div>
  {% endfor %}
</div>

{% if site.projects.size == 0 %}
<div class="coming-soon">
  <h2>🚀 More Projects Coming Soon!</h2>
  <p>We're currently working on showcasing our portfolio. Check back soon to see the innovative solutions we've delivered for our clients.</p>
  <p>In the meantime, feel free to <a href="{{ '/contact.html' | relative_url }}">contact us</a> to discuss your project needs.</p>
</div>
{% endif %}

---

## Looking for Something Specific?

Whether you need a web application, mobile app, cloud solution, or custom software, we have the expertise to deliver.

[View Our Services](/services/){: .btn .btn-primary} [Contact Us](/contact/){: .btn .btn-secondary}
