---
layout: default
permalink: /ruby/
title: "About  Ruby 📚"
description: "Programming tutorials and guides focused on Ruby, especially in the context of static site development with the Jekyll framework. Learn how to build and customize your blog."
keywords: "Ruby, Jekyll, Ruby programming, static site development, opencodecl, Jekyll tutorials, Ruby guide"
---


<p class="lead">
  Here you will find tutorials, guides, and resources focused on programming with Ruby,
  especially in the context of static site development with Jekyll.
</p>

<div class="row">
  {% assign jekyll_posts = site.posts | where: 'tags', 'jekyll' | reverse %}

  {% if jekyll_posts.size > 0 %}

    {% for post in jekyll_posts %}

      <div class="col-12 mb-4">
        <div class="card h-100 shadow-sm position-relative">

          <div class="card-header">

            <h5 class="mb-0">
                <a href="{{ post.url | relative_url }}" class="text-danger">
                    {{ post.title }}
                </a>
            </h5>
          </div>

          <div class="card-body">
            <p class="card-text">
                {{ post.description | default: post.excerpt | strip_html | truncatewords: 30 }}
            </p>
            <a href="{{ post.url | relative_url }}" class="stretched-link"></a>
          </div>

          <div class="card-footer bg-secondary text-white">
            Published on {{ post.date | date: "%Y-%m-%d" }}
            <br>

          </div>

        </div>
      </div>

    {% endfor %}

  {% else %}
    <div class="col-12">
      <div class="alert alert-warning" role="alert">
        There are no posts yet with the "Jekyll" tag. They are on the way!
      </div>
    </div>
  {% endif %}
</div>
