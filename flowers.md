---
layout: page
title: Flowers for you!!
---

<div id="image-container">
    <img id="random-image" alt="Random Flower" />
</div>

<script>
// Array of image file paths in the /img/flowers directory
const images = [
    {% for image in site.static_files %}
      {% if image.path contains '/img/flowers/' %}
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

// Load a random image immediately when the page loads
window.onload = loadRandomImage;
</script>
