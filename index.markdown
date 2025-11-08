---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---
# News

<div class="row pt-4">
  {% for post in site.posts %}

    {%- assign post_date = post.date | date: "%s" -%}
    {%- assign current_date = 'now' | date: "%s" -%}

    {% if post_date <= current_date %}

      <div class="col-md-6 mb-4">
        <div class="card h-100 shadow-sm text-light">

          <div class="card-header">
            <h5 class="mb-0">{{ post.title }}</h5>
          </div>

          <div class="card-body ">
            <p class="card-text">{{post.excerpt | strip_html | truncatewords: 30}}</p>
            <a href="{{ post.url | relative_url }}" class="btn btn-primary mt-2">
              Read more
            </a>
          </div>

          <div class="card-footer">
            Published on: {{ post.date | date: "%Y-%m-%d" }}
          </div>

        </div>
      </div>

    {% endif %}
  {% endfor %}
</div>
