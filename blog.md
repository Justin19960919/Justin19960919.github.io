---
layout: default
title: Blog
description: Latest blog posts
---

<main class="main-content fadeInDown delay_075s">

  {% for post in site.posts %}
  <article class="post">
    <header class="post-header">
      <time class="post-date" datetime="{{ post.date | date: "%Y-%m-%d" }}">{{post.date | date: "%B %-d, %Y" }}</time>
      <h2 class="post-title"><a href="{{ site.baseurl }}{{ post.url }}" rel="bookmark">{{post.title}}</a></h2>
      <div class="post-meta">
        By <span class="post-author">{{ site.data.author.name }}</span>
      </div><!-- .post-meta -->
      {% if post.feature_image and post.feature_image != "" %}
      <figure class="post-thumbnail image-card width-wide">
        <a href="{{site.baseurl}}{{post.url}}"><img src="{{ post.feature_image | relative_url }}"
            alt="{{ post.title }}"></a>
      </figure><!-- .post-thumbnail -->
      {% endif %}
    </header><!-- .post-header -->
    <div class="post-content">
      {% if post.content contains '<!--more-->' %}
      {{ post.content | split:'<!--more-->' | first }}
      <p class="read-more"><a href="{{ site.baseurl }}{{ post.url }}" class="read-more-link">Continue reading &rarr;</a>
      </p>
      {% else %}
      {{ post.content }}
      {% endif %}
    </div><!-- .post-content -->
  </article><!-- .post -->
  {% endfor %}



</main><!-- .site-main -->

