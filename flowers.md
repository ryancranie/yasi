---
layout: page
title: Flowers for you!!
---

<!-- This div will display the message about the flower number -->
<p id="flower-message" style="text-align: center; font-size: 18px; margin-top: 15px;"></p>

<!-- Styled button to load a new random image -->
<button id="new-flower-button" onclick="loadRandomImage()">Show Another Flower</button>

<div id="image-container" style="text-align: center; margin-top: 20px;">
    <img id="random-image" alt="Random Flower" style="max-width: 100%; height: auto;" />
</div>

<script>
// Array of image file paths in the /img/flowers directory, accounting for the base URL
const images = [
    {% for image in site.static_files %}
      {% if image.path contains '/img/flowers/' %}
        "{{ site.baseurl }}{{ image.path }}",
      {% endif %}
    {% endfor %}
];

// Function to select a random image and display it, with a message
function loadRandomImage() {
    const randomIndex = Math.floor(Math.random() * images.length); // Get a random index
    const randomImage = images[randomIndex]; // Get the image path based on random index
    document.getElementById('random-image').src = randomImage; // Set the image source
    
    // Display a message about which flower was selected
    document.getElementById('flower-message').textContent = `You landed on flower ${randomIndex + 1}`;
}

// Load a random image immediately when the page loads
window.onload = loadRandomImage;
</script>

<!-- Styling for the button -->
<style>
  #new-flower-button {
      background-color: rgb(172, 65, 66); /* Red background */
      color: white; /* White text */
      border: none; /* Remove border */
      padding: 10px 20px; /* Padding for the button */
      font-size: 16px; /* Increase font size */
      border-radius: 5px; /* Rounded corners */
      cursor: pointer; /* Pointer cursor on hover */
      transition: background-color 0.3s ease; /* Smooth hover effect */
      display: block; /* Block element for centering */
      margin: 20px auto; /* Center the button */
  }

  #new-flower-button:hover {
      background-color: rgb(172, 65, 66); /* Slightly lighter pink on hover */
  }

  /* Center the image container */
  #image-container {
      text-align: center; /* Center the image */
      margin-top: 20px; /* Spacing above the image */
  }

  /* Ensure the image is responsive */
  #random-image {
      max-width: 100%; /* Scale the image to fit its container */
      height: auto; /* Maintain aspect ratio */
      display: block; /* Ensure it's treated as a block element for centering */
      margin: 0 auto; /* Center the image horizontally */
  }
</style>