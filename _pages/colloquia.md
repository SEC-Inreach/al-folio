---
layout: page
title: colloquia
permalink: /colloquia/
description: SEC-Inreach presents: "Big Questions in Particle Physics"
nav: true
---

The <a href="https://snowmass21.org/">Snowmass 2021</a> process provides an opportunity for the  particle physics community to come together to identify and document a scientific vision for the future of particle physics in the US and around the world during the next tenyears. But what about the future beyond that? Which questions will young researchers spend their careers working to address, and what are the best paths towards the answers?

The <b>Big Questions in Particle Physics</b> colloqium series is trying to help early-career researchers reflect on the long-term future of particle physics. Each colloquim features a pair of speakers with different backgrounds, who will discuss comlementary approaches towards these Big Questions. 

<div class="projects grid">

  {% assign sorted_colloquia = site.colloquia | sort: "importance" %}
  {% for project in sorted_colloquia %}
  <div class="grid-item">
    {% if project.redirect %}
    <a href="{{ project.redirect }}" target="_blank">
    {% else %}
    <a href="{{ project.url | relative_url }}">
    {% endif %}
      <div class="card hoverable">
        {% if project.img %}
        <img src="{{ project.img | relative_url }}" alt="project thumbnail">
        {% endif %}
        <div class="card-body">
          <h2 class="card-title text-lowercase">{{ project.title }}</h2>
          <p class="card-text">{{ project.description }}</p>
          <div class="row ml-1 mr-1 p-0">
            {% if project.github %}
            <div class="github-icon">
              <div class="icon" data-toggle="tooltip" title="Code Repository">
                <a href="{{ project.github }}" target="_blank"><i class="fab fa-github gh-icon"></i></a>
              </div>
              {% if project.github_stars %}
              <span class="stars" data-toggle="tooltip" title="GitHub Stars">
                <i class="fas fa-star"></i>
                <span id="{{ project.github_stars }}-stars"></span>
              </span>
              {% endif %}
            </div>
            {% endif %}
          </div>
        </div>
      </div>
    </a>
  </div>
{% endfor %}

</div>
