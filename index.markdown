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
        <div class="card h-100 shadow-lg text-light rounded-4">

          <div class="card-header">
            <h5 class="mb-0">{{ post.title }}</h5>
          </div>

          <div class="card-body ">
            <p class="card-text">{{post.excerpt | strip_html | truncatewords: 30}}</p>
            <a href="{{ post.url | relative_url }}" class="btn btn-primary mt-2">
              Read more
            </a>
          </div>

         <div class="card-footer d-flex justify-content-between align-items-center">

            <small class="text-light">
              Published on: {{ post.date | date: "%Y-%m-%d" }}
            </small>

            {% if post.tags.size > 0 %}
              <div>
                {% for tag in post.tags %}
                  <span class="badge text-bg-primary rounded-pill ms-1">
                    {{ tag }}
                  </span>
                {% endfor %}
              </div>
            {% endif %}

          </div>

        </div>
      </div>

    {% endif %}
  {% endfor %}
</div>
