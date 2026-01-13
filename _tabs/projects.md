---
layout: default
icon: fas fa-gamepad
order: 1
---

<article class="px-1">
    <h1>Projects</h1>
    <div id="post-list" class="flex-grow-1 px-xl-1">
    {% for post in site.projects %}
        <article class="card-wrapper card">
        <a href="{{ post.url | relative_url }}" class="post-preview row g-0">
            {% assign card_body_col = '12' %}

            <div class="col-md-{{ card_body_col }}">
            <div class="card-body d-flex flex-column">
                <h1 class="card-title my-2 mt-md-0">{{ post.title }}</h1>
                <div class="card-text content mt-0 mb-3">
                <p>{% include post-summary.html %}</p>
                </div>
                <!-- .post-meta -->
            </div>
            <!-- .card-body -->
            </div>
        </a>
        </article>
    {% endfor %}
    </div>
    <!-- #post-list -->
</article>
