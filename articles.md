---
layout: page
---

<!-- Filter Options -->
<div class="filter-options">
  <button onclick="filterPosts('all')">All Posts</button>
  <button onclick="filterPosts('regular')">Regular Posts</button>
  <button onclick="filterPosts('dark')">Dark Posts</button>
</div>

{% assign posts = paginator.posts | default: site.posts %}

<!-- role="list" needed so that `list-style: none` in Safari doesn't remove the list semantics -->
<ul class="posts-list list-unstyled" role="list">
  {% for post in posts %}
    {% assign isRegularPost = post.dark != true %}
    {% assign isDarkPost = post.dark == true %}

    {% if isRegularPost or isDarkPost %}
      <li class="post-preview" {% if isRegularPost %}id="regularPosts"{% elsif isDarkPost %}id="darkPosts"{% endif %}>
        <article>

          {%- capture thumbnail -%}
            {% if post.thumbnail-img %}
              {{ post.thumbnail-img }}
            {% elsif post.cover-img %}
              {% if post.cover-img.first %}
                {{ post.cover-img[0].first.first }}
              {% else %}
                {{ post.cover-img }}
              {% endif %}
            {% else %}
            {% endif %}
          {% endcapture %}
          {% assign thumbnail=thumbnail | strip %}

          {% if site.feed_show_excerpt == false %}
          {% if thumbnail != "" %}
          <div class="post-image post-image-normal">
            <a href="{{ post.url | absolute_url }}" aria-label="Thumbnail">
              <img src="{{ thumbnail | absolute_url }}" alt="Post thumbnail">
            </a>
          </div>
          {% endif %}
          {% endif %}

          <a href="{{ post.url | absolute_url }}">
            <h2 class="post-title">{{ post.title | strip_html }}</h2>

            {% if post.subtitle %}
              <h3 class="post-subtitle">
              {{ post.subtitle | strip_html }}
              </h3>
            {% endif %}
          </a>

          {% if post.author %}
            <span>By <strong>{{ post.author | strip_html }}</strong></span>
          {% endif %}
          <p class="post-meta">
            {% assign date_format = site.date_format | default: "%B %-d, %Y" %}
            Posted on {{ post.date | date: date_format }}
          </p>

          {% if thumbnail != "" %}
          <div class="post-image post-image-small">
            <a href="{{ post.url | absolute_url }}" aria-label="Thumbnail">
              <img src="{{ thumbnail | absolute_url }}" alt="Post thumbnail">
            </a>
          </div>
          {% endif %}

          {% unless site.feed_show_excerpt == false %}
          {% if thumbnail != "" %}
          <div class="post-image post-image-short">
            <a href="{{ post.url | absolute_url }}" aria-label="Thumbnail">
              <img src="{{ thumbnail | absolute_url }}" alt="Post thumbnail">
            </a>
          </div>
          {% endif %}

          <div class="post-entry">
            {% assign excerpt_length = site.excerpt_length | default: 50 %}
            {{ post.excerpt | strip_html | truncatewords: excerpt_length }}
            {% assign excerpt_word_count = post.excerpt | number_of_words %}
            {% if post.content != post.excerpt or excerpt_word_count > excerpt_length %}
              <a href="{{ post.url | absolute_url }}" class="post-read-more">[Read&nbsp;More]</a>
            {% endif %}
          </div>
          {% endunless %}

          {% if site.feed_show_tags != false and post.tags.size > 0 %}
          <div class="blog-tags">
            <span>Tags:</span>
            <!-- role="list" needed so that `list-style: none` in Safari doesn't remove the list semantics -->
            <ul class="d-inline list-inline" role="list">
              {% for tag in post.tags %}
              <li class="list-inline-item">
                <a href="{{ '/tags' | absolute_url }}#{{- tag -}}">{{- tag -}}</a>
              </li>
              {% endfor %}
            </ul>
          </div>
          {% endif %}

        </article>
      </li>
    {% endif %}
  {% endfor %}
</ul>

{% if paginator.total_pages > 1 %}
<ul class="pagination main-pager">
  {% if paginator.previous_page %}
  <li class="page-item previous">
    <a class="page-link" href="{{ paginator.previous_page_path | absolute_url }}">
      <i class="fas fa-arrow-left" alt="Newer Posts"></i>
      <span class="d-none d-sm-inline-block">Newer Posts</span>
    </a>
  </li>
  {% endif %}
  {% if paginator.next_page %}
  <li class="page-item next">
    <a class="page-link" href="{{ paginator.next_page_path | absolute_url }}">
      <span class="d-none d-sm-inline-block">Older Posts</span>
      <i class="fas fa-arrow-right" alt="Older Posts"></i>
    </a>
  </li>
  {% endif %}
</ul>
{% endif %}

<script>
  function filterPosts(filterType) {
    const regularPosts = document.getElementById('regularPosts');
    const darkPosts = document.getElementById('darkPosts');

    if (filterType === 'all') {
      regularPosts.style.display = 'block';
      darkPosts.style.display = 'block';
    } else if (filterType === 'regular') {
      regularPosts.style.display = 'block';
      darkPosts.style.display = 'none';
    } else if (filterType === 'dark') {
      regularPosts.style.display = 'none';
      darkPosts.style.display = 'block';
    }
  }
</script>
