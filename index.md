---
layout: default
title: "Home"
---

<section class="hero hero-home">
  <p class="eyebrow">A seasonal soundtrack</p>
  <h1>Top 10 songs of the summer</h1>
  <p class="hero-lede">Introduce your project here with a short description of your selections, listening criteria, and editorial point of view.</p>
</section>

<section class="intro-section" aria-labelledby="intro-heading">
  <div>
    <p class="eyebrow">About the list</p>
    <h2 id="intro-heading">Your summer, ranked.</h2>
  </div>
  <div class="intro-copy">
    <p>Use this space to explain how you created the countdown and what makes a song feel like a song of the summer.</p>
    <p>Add your publication date, playlist link, or any other project details here.</p>
  </div>
</section>

<section class="ranking-section" aria-labelledby="ranking-heading">
  <div class="section-heading">
    <p class="eyebrow">The countdown</p>
    <h2 id="ranking-heading">The top 10</h2>
  </div>
  <div class="song-grid">
    {% assign ranked_songs = site.songs | sort: "rank" %}
    {% for song in ranked_songs %}
      <a class="song-card" href="{{ song.url | relative_url }}">
        <span class="card-rank">{{ song.rank | prepend: "0" | slice: -2, 2 }}</span>
        <div class="card-art {% unless song.cover_image %}card-art-placeholder{% endunless %}">
          {% if song.cover_image %}
            <img src="{{ song.cover_image | relative_url }}" alt="{{ song.cover_alt }}" loading="lazy">
          {% else %}
            <span>Cover art<br>placeholder</span>
          {% endif %}
        </div>
        <div class="card-info">
          <h3>{{ song.title }}</h3>
          <p>{{ song.performer }}</p>
          <span class="text-link">Read review <span aria-hidden="true">↗</span></span>
        </div>
      </a>
    {% endfor %}
  </div>
</section>
