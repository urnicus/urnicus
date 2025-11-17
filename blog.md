---
layout: default
title: Voter Data Blog
permalink: /blog/
---

# Voter Data Access Guide

Welcome to the Voter Data Access Guide. This blog provides comprehensive, state-by-state information on how to obtain voter registration lists and voter history data across the United States.

## All Posts

{% if site.posts.size > 0 %}
<ul class="post-list">
  {% for post in site.posts %}
    <li class="post-item">
      <span class="post-date">{{ post.date | date: "%b %-d, %Y" }}</span>
      <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
{% else %}
<p>No posts yet. Check back soon!</p>
{% endif %}

<style>
  .post-list {
    list-style: none;
    padding: 0;
    margin: 2rem 0;
  }

  .post-item {
    margin: 1rem 0;
    padding: 0.75rem 0;
    border-bottom: 1px solid #e1e4e8;
  }

  .post-date {
    color: #586069;
    font-size: 0.9rem;
    margin-right: 1rem;
    display: inline-block;
    min-width: 100px;
  }

  .post-link {
    font-size: 1.1rem;
    font-weight: 500;
    text-decoration: none;
  }

  .post-link:hover {
    text-decoration: underline;
  }
</style>
