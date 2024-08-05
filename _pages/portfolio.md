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
    <h3 class="project-title">{{ project.title }}</h3>
    <p class="short-description">{{ project.short_description }}</p>
    <img src="{{ project.image }}" alt="{{ project.title }} Image" class="portfolio-image">

    <details class="project-details">
      <summary>Description</summary>
      <p>{{ project.full_description }}</p>

      <!-- Code Link -->
      {% if project.code_link and project.code_link != false %}
        <p>
          <strong>{{ project.code_title | default: "Code" }}:</strong> 
          <a href="{{ project.code_link }}" target="_blank">
            {{ project.code_text | default: "View on GitHub" }}
          </a>
        </p>
      {% elsif project.code_title or project.code_text %}
        <p>
          <strong>{{ project.code_title | default: "Code" }}:</strong> 
          {{ project.code_text | default: "" }}
        </p>
      {% endif %}

      <!-- Report Link -->
      {% if project.report_link and project.report_link != false %}
        <p>
          <strong>{{ project.report_title | default: "Report" }}:</strong> 
          <a href="{{ project.report_link }}" target="_blank">
            {{ project.report_text | default: "Read the Report" }}
          </a>
        </p>
      {% elsif project.report_title or project.report_text %}
        <p>
          <strong>{{ project.report_title | default: "Report" }}:</strong> 
          {{ project.report_text | default: "" }}
        </p>
      {% endif %}

      <!-- Presentation Link -->
      {% if project.presentation_link and project.presentation_link != false %}
        <p>
          <strong>{{ project.presentation_title | default: "Presentation" }}:</strong> 
          <a href="{{ project.presentation_link }}" target="_blank">
            {{ project.presentation_text | default: "View Presentation" }}
          </a>
        </p>
      {% elsif project.presentation_title or project.presentation_text %}
        <p>
          <strong>{{ project.presentation_title | default: "Presentation" }}:</strong> 
          {{ project.presentation_text | default: "" }}
        </p>
      {% endif %}
      
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