---
layout: page
title: Projects
---

Coming Soon...

<style>
ul {
  display: flex;
  flex-wrap: wrap; /* Allows items to wrap onto the next line */
  padding: 0; /* Removes padding */
  margin: 0; /* Removes margin */
  list-style-type: none; /* Removes bullet points */
}

.project-item {
  flex: 1 1 300px; /* Flex-grow, flex-shrink, and flex-basis */
  margin: 10px; /* Spacing between items */
  box-sizing: border-box; /* Includes padding and border in the element's total width and height */
  position: relative;
  overflow: hidden; /* Ensures nothing spills out of the container */
}

.project-item img {
  width: 100%;
  height: auto; /* Maintain aspect ratio */
  transition: filter 0.3s;
}

.project-item:hover img {
  filter: grayscale(50%); /* Gray out the image */
}

.project-title {
  position: absolute;
  width: 100%;
  bottom: 0;
  left: 0;
  background-color: rgba(0, 0, 0, 0.5); /* Semi-transparent black background */
  color: white;
  text-align: center;
  padding: 10px 0; /* Padding for better visual */
  visibility: hidden;
  opacity: 0;
  transition: opacity 0.3s, visibility 0.3s;
}

.project-item:hover .project-title {
  visibility: visible;
  opacity: 1;
}
</style>

<ul>
  {% for post in site.posts %}
    {% if post.categories contains 'projects' %}
      <li class="project-item">
        <a href="{{ post.url | relative_url }}">
          <img src="{{ post.image | relative_url }}" alt="{{ post.title }}">
          <div class="project-title">{{ post.title }}</div>
        </a>
      </li>
    {% endif %}
  {% endfor %}
</ul>
