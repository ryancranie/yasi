---
layout: page
title: Flowers for you!!
---

<div id="image-container">
    <img id="random-image" alt="Random Flower" />
</div>
<br>
<button onclick="loadRandomImage()">Load Another Random Image</button>

<script>
// Array of image file names in the /img/flowers directory (filtering by file type)
const images = [
    {% for image in site.static_files %}
      {% if image.path contains '/img/flowers/' and (image.extname == '.png' or image.extname == '.jpg' or image.extname == '.jpeg' or image.extname == '.gif') %}
        "{{ image.path }}",
      {% endif %}
    {% endfor %}
];

// Function to select a random image and display it
function loadRandomImage() {
    const randomIndex = Math.floor(Math.random() * images.length);
    const randomImage = images[randomIndex];
    document.getElementById('random-image').src = randomImage;
}

// Load a random image on page load
loadRandomImage();
</script>