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

<div class="portfolio-container">
  {% for project in projects %}
  <div class="portfolio-item">
    <h3 class="project-title">{{ project.title }}</h3> <!-- Using <h3> for titles -->
    <p class="short-description">{{ project.short_description }}</p>
    <img src="{{ project.image }}" alt="{{ project.title }} Image" class="portfolio-image">

    <details class="project-details">
      <summary>Description</summary>
      <p>{{ project.full_description }}</p>
      
      <!-- Conditionally display links if available -->
      {% if project.code_link %}
      <p><strong>Code:</strong> <a href="{{ project.code_link }}" target="_blank">View on GitHub</a></p>
      {% endif %}

      {% if project.report_link %}
      <p><strong>Report:</strong> <a href="{{ project.report_link }}" target="_blank">Read the Report</a></p>
      {% endif %}

      {% if project.presentation_link %}
      <p><strong>Presentation:</strong> <a href="{{ project.presentation_link }}" target="_blank">View Presentation</a></p>
      {% endif %}
    </details>
  </div>
  {% endfor %}
</div>

<style>
  .portfolio-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 20px;
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
    text-decoration: underline;
  }
</style>