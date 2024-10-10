---
layout: page
title: Dear Yasi
---

# Our Time Together

testetsetsets

<p id="together-time">
  <strong>Days:</strong> <span id="days"></span><br>
  <strong>Hours:</strong> <span id="hours"></span><br>
  <strong>Minutes:</strong> <span id="minutes"></span><br>
  <strong>Seconds:</strong> <span id="seconds"></span>
</p>

<script>
  // Set the date you started dating (year, month-1, day)
  const startDate = new Date(2023, 9, 20); // Example: November 10, 2022

  function updateCountdown() {
    const now = new Date();
    const diff = now - startDate;
    
    const seconds = Math.floor(diff / 1000);
    const minutes = Math.floor(seconds / 60);
    const hours = Math.floor(minutes / 60);
    const days = Math.floor(hours / 24);

    // Update HTML elements with the calculated time
    document.getElementById('days').textContent = days;
    document.getElementById('hours').textContent = hours;
    document.getElementById('minutes').textContent = minutes;
    document.getElementById('seconds').textContent = seconds;
  }

  // Update the countdown every second
  setInterval(updateCountdown, 1000);
</script>