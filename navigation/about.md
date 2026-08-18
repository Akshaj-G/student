---
layout: post
title: About
permalink: /about/
comments: true
---

# About Me

## As a Conversation Starter

Here are places connected to my heritage and life.

<div id="grid_container"></div>

<script>
  var outputElement = document.getElementById("grid_container");
  outputElement.innerHTML = '';

  // Data array for flags
  const living_in_the_world = [
    {
      flag: "https://upload.wikimedia.org/wikipedia/commons/4/41/Flag_of_India.svg",
      greeting: "Namaste",
      description: "India - Cultural Heritage"
    },
    {
      flag: "https://upload.wikimedia.org/wikipedia/commons/0/01/Flag_of_California.svg",
      greeting: "Hey",
      description: "California - Golden State"
    },
    {
      flag: "https://upload.wikimedia.org/wikipedia/commons/a/a4/Flag_of_the_United_States.svg",
      greeting: "Hello",
      description: "United States - Home"
    }
  ];

  // Create grid container
  const container = document.createElement('div');
  container.id = 'grid_container_inner';
  container.style.display = 'grid';
  container.style.gridTemplateColumns = 'repeat(auto-fill, minmax(180px, 1fr))';
  container.style.gap = '15px';
  container.style.padding = '10px 0';

  // Loop through flag data
  for (const location of living_in_the_world) {
    const item = document.createElement('div');
    item.style.border = '1px solid #ccc';
    item.style.borderRadius = '8px';
    item.style.padding = '12px';
    item.style.textAlign = 'center';
    item.style.boxShadow = '0 2px 5px rgba(0,0,0,0.1)';

    const img = document.createElement('img');
    img.src = location.flag;
    img.alt = location.description;
    img.style.width = '100%';
    img.style.height = '100px';
    img.style.objectFit = 'cover';
    img.style.borderRadius = '4px';

    const desc = document.createElement('p');
    desc.textContent = location.description;
    desc.style.fontWeight = 'bold';
    desc.style.margin = '8px 0 4px 0';

    const greet = document.createElement('p');
    greet.textContent = location.greeting;
    greet.style.margin = '0';
    greet.style.color = '#555';

    item.appendChild(img);
    item.appendChild(desc);
    item.appendChild(greet);
    container.appendChild(item);
  }

  outputElement.appendChild(container);
</script>

---

## Journey through Life

* 🏫 **Solana Pacific Elementary School** — Built my foundation during early childhood.
* 🏫 **Oak Valley Middle School** — Developed new interests, made lifelong friends, and grew academically.
* 🎓 **Del Norte High School** — Current student focused on academics, athletics, and preparing for future goals.

### Sports & Extracurriculars

* ⚽ **Athletics & Sports** — Active in team sports, maintaining fitness, competitive spirit, and teamwork.
* 📚 **Academics & STEM** — Exploring coursework in science, mathematics, and computer science.

---

## Photo Gallery

*Scroll to the right for more memories...*

<div class="image-gallery">
  <img src="/images/about/team-photo.png" alt="Del Norte High School">
</div>

<style>
  .image-gallery {
    display: flex;
    flex-wrap: nowrap;
    overflow-x: auto;
    gap: 12px;
    padding: 10px 0;
  }
  .image-gallery img {
    max-height: 180px;
    object-fit: cover;
    border-radius: 8px;
    border: 1px solid #ddd;
  }
</style>