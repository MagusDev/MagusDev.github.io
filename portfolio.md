---
title: Projects
subtitle: Here are some of the projects I've done
---
<style>
  .projects-container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px; /* Adjust the gap between items */
    /* Optional: You can add more styling as needed */
  }

  .project-item {
    width: calc(33.33% - 20px); /* 33.33% width for each column with gap adjustment */
    padding: 15px; /* Padding around each project item */
    border: 1px solid #eaeaea; /* Border for each project item */
    border-radius: 5px; /* Optional: Rounded corners */
    /* Optional: You can add more styling as needed */
  }

  .project-item img {
    width: 100%; /* Ensures the image takes the full width of its container */
    height: auto; /* Maintains aspect ratio */
    /* Optional: You can add more styling as needed */
  }

  /* Media query for mobile devices */
  @media (max-width: 767px) {
    .projects-container {
      justify-content: center; /* Center items */
    }

    .project-item {
      width: 100%; /* Full width on mobile */
      max-width: 400px; /* Optional: Limit the maximum width */
      /* Additional mobile-specific styling */
    }
  }
</style>

<div class="projects-container">
  {% for project in site.data.projects %}
    <div class="project-item">
      <img src="{{ project.image_url }}" alt="{{ project.name }}">
      <h3><a href="{{ project.github_link }}">{{ project.name }}</a></h3>
      <p>{{ project.description }}</p>
    </div>
  {% endfor %}
</div>