---
title:  "Portfolio"
layout: collection
permalink: /portfolio/
collection: portfolio
entries_layout: grid
classes: wide
header:
  overlay_color: "#5e616c"
  overlay_image: /assets/images/oksana-maselko-tkuUS11XyaA-unsplash.jpg
  image_description: "Picture of a pile of yarn skeins with the words: Portfolio."

---

{% include base_path %}

<div class="grid__wrapper">
  {% for post in site.portfolio %}
    {% include archive-single.html type="grid" %}
  {% endfor %}
</div>

<h5 style="text-align: center;">Interested in learning more or collaborating? <em>Let's connect!</em></h5>

