---
layout: default
permalink: /graphic-design/
---

# Graphic Design

<p class="lead">
  Here you will find tutorials, guides, and resources dedicated to Graphic Design. Whether you are mastering open-source tools like GIMP or exploring general visual principles, these contents are perfect for complementing your work in Jekyll and Ubuntu.
</p>

<div class="row">
  {% assign gimp_posts = site.posts | where: 'tag', 'graphic' %}

  {% if gimp_posts.size > 0 %}

    {% for post in gimp_posts %}

      <div class="col-md-6 mb-4">
        <div class="card h-100 shadow-sm">

          <div class="card-header">
            <h5 class="mb-0">{{ post.title }}</h5>
          </div>

          <div class="card-body">
            <p class="card-text">
              {{ post.description | default: post.excerpt | strip_html | truncatewords: 30 }}
            </p>

            <a href="{{ post.url | relative_url }}" class="btn btn-primary mt-2">
              Read Full Article
            </a>
          </div>

          <div class="card-footer">
            Published on {{ post.date | date: "%Y-%m-%d" }}
            <br>
            <small>Tags:
              {% for tag in post.tags %}
                {% if tag == "gimp" %}
                  <span class="badge bg-primary">{{ tag }}</span>
                {% else %}
                  <span class="badge bg-secondary">{{ tag }}</span>
                {% endif %}
              {% endfor %}
            </small>
          </div>
        </div>
      </div>

    {% endfor %}

  {% else %}
    <div class="col-12">
      <div class="alert alert-warning" role="alert">
        There are no posts yet with the "GIMP" tag. They are on the way!
      </div>
    </div>
  {% endif %}
</div>
