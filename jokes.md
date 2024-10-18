---
layout: page
title: Dad Jokes for You!
---

<div id="joke-container" style="text-align: center;">
    <p id="joke-setup" style="font-size: 24px;"></p> <!-- Increased font size -->
    <button id="show-answer-button" onclick="toggleAnswer()" style="display: none;">Show Answer</button>
    <p id="joke-punchline" style="font-size: 24px; display: none;"></p> <!-- Increased font size -->
</div>

<br>

<!-- Button container for alignment -->
<div style="text-align: center;">
    <button id="new-joke-button" onclick="loadRandomJoke()">Generate New Joke</button>
</div>

<script>
// Fetch the jokes from the YAML data
const jokes = [
    {% for joke in site.data.jokes %}
      { "setup": "{{ joke.setup }}", "punchline": "{{ joke.punchline }}" },
    {% endfor %}
];

// Function to load a random joke
function loadRandomJoke() {
    const randomIndex = Math.floor(Math.random() * jokes.length);
    const randomJoke = jokes[randomIndex];
    
    document.getElementById('joke-setup').textContent = randomJoke.setup;
    document.getElementById('joke-punchline').textContent = randomJoke.punchline;
    document.getElementById('show-answer-button').style.display = "inline-block"; // Show answer button
    document.getElementById('joke-punchline').style.display = "none"; // Hide punchline initially
}

// Function to toggle the display of the joke's punchline
function toggleAnswer() {
    const punchlineElement = document.getElementById('joke-punchline');
    if (punchlineElement.style.display === "none") {
        punchlineElement.style.display = "block"; // Show the punchline
    } else {
        punchlineElement.style.display = "none"; // Hide the punchline
    }
}

// Load a random joke immediately when the page loads
window.onload = loadRandomJoke;
</script>

<!-- Styling for the buttons -->
<style>
  #new-joke-button, #show-answer-button {
      background-color: rgb(172, 65, 66); /* Updated button color */
      color: white; /* White text */
      border: none; /* Remove border */
      padding: 10px 20px; /* Padding for the button */
      font-size: 18px; /* Increased font size */
      border-radius: 5px; /* Rounded corners */
      cursor: pointer; /* Pointer cursor on hover */
      transition: background-color 0.3s ease; /* Smooth hover effect */
      margin: 10px; /* Margin around buttons */
  }

  #new-joke-button:hover, #show-answer-button:hover {
      background-color: rgb(192, 80, 81); /* Slightly lighter shade on hover */
  }

  #joke-container {
      margin-top: 20px; /* Spacing above the jokes */
  }

  /* Flexbox for button alignment */
  .button-container {
      display: flex; /* Use flexbox for alignment */
      justify-content: center; /* Center the buttons */
      gap: 10px; /* Space between buttons */
  }
</style>
