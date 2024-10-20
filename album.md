---
layout: page
title: Photo Album
---

Here are my favourite pictures of us!

{% assign album_images = site.static_files | where_exp: "item", "item.path contains '/img/album/'" %}

{% for image in album_images %}
  {% if image.extname == '.png' or image.extname == '.jpg' or image.extname == '.jpeg' or image.extname == '.gif' %}
    <img src="{{ site.baseurl }}{{ image.path }}" style="width: 600px; height: auto;">
  {% endif %}
{% endfor %}

I wuv u mostest