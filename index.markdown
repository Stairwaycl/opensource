---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---
# News

<ul>
  {% for post in site.posts %}

    {%- assign post_date = post.date | date: "%s" -%}
    {%- assign current_date = 'now' | date: "%s" -%}
    {% if post_date <= current_date %}

      <lu>
        <div class="card text-center">
          <div class="card-header">
          </div>
          <div class="card-body">
            <h5 class="card-title">{{ post.title }}</h5>
            <p class="card-text">{{post.excerpt}}</p>
            <a href="{{post.url}}" class="btn btn-primary">Read more</a>
          </div>
          <div class="card-footer text-body-secondary">
            {{ post.date | date: "%s" | times: 1 | date: "%Y-%m-%d %H:%M:%S" | timeago }}
          </div>
        </div>
      </lu>

    {% endif %}
  {% endfor %}
</ul>
