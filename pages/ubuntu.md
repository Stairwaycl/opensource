---
layout: default
permalink: /ubuntu/
---

# Ubuntu Course

<p class="lead">
  Here you will find tutorials, guides, and resources on Ubuntu Linux OS, the open-source operating system we use in our workflow for development with Jekyll, VS Code, and other tools.
</p>

<div class="row">
  {% assign ubuntu_posts = site.posts | where: 'tags', 'ubuntu' %}

  {% if ubuntu_posts.size > 0 %}

    {% for post in ubuntu_posts %}

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
                {% if tag == "ubuntu" %}
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
        There are no posts yet with the "Ubuntu" tag. They are on the way!
      </div>
    </div>
  {% endif %}
</div>
