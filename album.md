---
layout: page
title: Photo Album
---

Here are my favourite pictures of us!

{% assign album_images = site.static_files | where: "path", "/img/album" %}

{% for image in album_images %}
  <img src="{{ site.baseurl }}{{ image.path }}" style="width: 600px; height: auto;">
{% endfor %}

I wuv u mostest