---
layout: page
title: Blog
permalink: /blog/
---

Stay updated with the latest insights, tutorials, and news from K11 Software Solutions.

<div class="blog-posts">
  {% for post in site.posts %}
    <article class="blog-post-preview">
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <div class="post-meta">
        <span class="post-date">{{ post.date | date: "%B %d, %Y" }}</span>
        {% if post.author %}
          <span class="post-author">by {{ post.author }}</span>
        {% endif %}
      </div>
      <div class="post-excerpt">
        {{ post.excerpt }}
      </div>
      <a href="{{ post.url | relative_url }}" class="read-more">Read More →</a>
    </article>
  {% endfor %}
</div>

{% if site.posts.size == 0 %}
<div class="no-posts">
  <p>No blog posts yet. Check back soon for updates!</p>
</div>
{% endif %}
