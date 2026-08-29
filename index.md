---
title: {{ site.title }}
layout: default
---

<!-- HERO SECTION -->
<section class="hero is-medium is-custom-gradient has-text-white">
  <div class="hero-body">
    <div class="container">
      <div class="columns is-vcentered">
        <div class="column is-7">
          <span class="tag is-warning is-light mb-3 has-text-weight-bold">Open Source Initiative</span>
          <h1 class="title is-1 has-text-white">
            {{ site.tagline }}
          </h1>
          <h2 class="subtitle is-4 has-text-grey-light mt-3">
            {{ site.description }}
          </h2>
          <div class="buttons mt-5">
            <!-- <a class="button is-brand-orange is-medium">Explore Documentation</a> -->
            <a href="https://github.com/opencdsi" target="_blank" class="button is-outlined is-white is-medium">GitHub Repository</a>
          </div>
        </div>


        <div class="column is-5 has-text-centered">
          <!-- Decorative Visual Placeholder -->
            <img src="/assets/img/dark-logo.svg" width="250" height="250">
        </div>
      </div>
    </div>
  </div>
</section>

{% if site.show_products %}
{% include products.html %}
{% endif %}

<!-- BLOG & CONTACT SECTIONS (SPLIT GRID) -->
<section id="blog" class="section py-6">
  <div class="container">
    <div class="columns">
      
      <!-- Blog Teaser Column -->
      <div class="column is-6">
        <h2 class="title is-3 text-blue mb-5">Latest News</h2>
        
{% for post in site.posts limit:2 %}
{% include summary.html %}
{% endfor %}
        
        <a href="/posts/" class="button is-text pl-0 text-purple">View All Blog Posts &rarr;</a>
      </div>

      <!-- Contact Form Column -->
      <div id="contact" class="column is-5 is-offset-1">
        <div class="box p-5">
          <h2 class="title is-4 text-blue mb-4">Contact Us</h2>
            {%- if site.email -%}
            <li><a class="" href="mailto:{{ site.email }}">{{ site.email }}</a></li>
            {%- endif -%}
         
        </div>
      </div>

    </div>
  </div>
</section>

