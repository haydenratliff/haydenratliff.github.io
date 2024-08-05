---
layout: archive
title: "Portfolio"
permalink: /portfolio/
author_profile: true
redirect_from:
  - /portfolio
---

Welcome to my portfolio! Below are some of the projects I've worked on. Click on each project for more details.

{% include base_path %}

{% assign projects = site.data.portfolio %}
{% assign max_items = 10 %} <!-- Set a maximum number of items to loop through -->

<div class="portfolio-container">
  {% for project in projects %}
  <div class="portfolio-item">
    <h3 class="project-title">{{ project.title }}</h3>
    <p class="short-description">{{ project.short_description | markdownify }}</p>
    <img src="{{ project.image }}" alt="{{ project.title }} Image" class="portfolio-image">

    <details class="project-details">
      <summary>Description</summary>
      <p>{{ project.full_description | markdownify }}</p> <!-- Markdown for full description -->

      <!-- Dynamic Items with Markdown -->
      {% for i in (1..max_items) %}
        {% capture item_key %}item{{ i }}{% endcapture %}

        {% assign item_content = project[item_key] %}

        {% if item_content %}
          <p>{{ item_content | markdownify }}</p>
        {% endif %}
      {% endfor %}
      
    </details>
  </div>
  {% endfor %}
</div>

<style>
  .portfolio-container {
    display: grid;
    grid-template-columns: repeat(2, 1fr); /* Two items per row */
    gap: 20px; /* Space between items */
  }

  @media screen and (max-width: 768px) {
    .portfolio-container {
      grid-template-columns: 1fr; /* One item per row on smaller screens */
    }
  }

  .portfolio-item {
    background: #f7f7f7;
    padding: 15px;
    border-radius: 10px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    transition: box-shadow 0.3s ease;
    margin-top: 20px;
    margin-bottom: 20px;
  }

  .portfolio-item:hover {
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  }

  .portfolio-image {
    width: 100%;
    height: auto;
    border-radius: 5px;
    margin-bottom: 10px;
  }

  .project-title {
    font-size: 1.17em; /* Matches the size of ### (h3) in Markdown */
    font-weight: bold;
    margin-top: 0;
    margin-bottom: 10px;
  }

  .short-description {
    font-size: 1em; /* Standard font size */
    margin-bottom: 10px;
  }

  .project-details summary {
    cursor: pointer;
    font-weight: bold;
    font-size: 0.95em; /* Slightly smaller than short description */
    margin-bottom: 5px;
  }

  .project-details p {
    font-size: 0.9em; /* Smaller size for detail paragraphs */
    margin: 0 0 5px 0; /* Maintain small spacing between paragraphs */
  }

  .project-details p a {
    color: #3366cc;
    text-decoration: none;
    transition: color 0.2s ease;
  }

  .project-details p a:hover {
    color: #0056b3;
  }
</style>