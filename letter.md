---
layout: page
title: Dear Yasi,
---

Surprise!! I've fooled you into scanning a QR code, and now <strong>you are mine</strong>... I've stolen your signature, and embedded it onto this marriage certificate, sooo... gg...

<img src="{{ site.baseurl }}/img/marriage.png" style="width: 700px; height: auto;">

## Happy anniversary!!

Happy first anniversary baby!! 

You make me so happy, and I'm so fortunate to be called yours. 

### What's here?
So I thought to put a few things on the website,

1. Firstly, I created a <a href="https://ryancranie.com/yasi/">recollection</a>, I put some of our earliest memories on here, and I hope we can walk through them together! :)
2. Secondly, I gave you some extra <a href="https://ryancranie.com/yasi/flowers">flowers</a>, just click the button and you'll see more! Still though, this is simply not enough flowers for my baby.
3. Thirdly, I created a <a href="https://ryancranie.com/yasi/jokes">jokes page</a>; I figured we laughed a lot at those dumb dad jokes so I wanted us to joke about some more.
4. And lastly, I created a simple <a href="https://ryancranie.com/yasi/album">album</a>. I was exclusive and chose some of my favourite pictures of us to put here.

### Our Time Together
Here shows how much time we have been together!!

<p id="together-time">
  <strong>Days:</strong> <span id="days"></span><br>
  <strong>Hours:</strong> <span id="hours"></span><br>
  <strong>Minutes:</strong> <span id="minutes"></span><br>
  <strong>Seconds:</strong> <span id="seconds"></span>
</p>

<script>
  // Set the date you started dating (year, month-1, day)
  const startDate = new Date(2023, 9, 20);

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

### You're the best

I hope you enjoy this (took ages fr), I love you.
<br>
<strong>NOTE</strong>: <em>I can take down, and put up this site, whenever you want. It's no inconvinience to me, and is only meant to exist as long as you see it :).<em>