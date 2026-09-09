---
layout: page
title: Available Downloads
permalink: /downloads/
---

<dl>

      {%- for item in site.data.downloads -%}
      <dt><strong><a href="{{ item[1].url }}">{{ item[1].title }}</a></strong></dt>
      <dd>{{ item[1].description }}</dd>
      {%- endfor -%}
      
</dl>

