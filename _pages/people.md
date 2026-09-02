---
layout: page
permalink: /people/
title: People
description: Current supervision, former team members, and student research projects.
nav: true
nav_order: 4
---

<div class="people-page">
  <div class="people-intro">
    <p>I supervise and co-supervise doctoral, graduate, and undergraduate research at the interface of geomorphology, geophysics, remote sensing, and planetary science. These projects combine field observations, space-mission data, image analysis, seismology, numerical modeling, and machine learning.</p>
    <p>Research topics span mass wasting and sediment transport on Earth; active surface processes on Mars, Titan, and the Moon; and mission-driven environmental seismology.</p>
  </div>

  <section class="people-section" aria-labelledby="current-supervision">
    <h2 id="current-supervision">Current doctoral supervision</h2>
    <div class="people-card-grid">
      {% for person in site.data.people.current_supervision %}
        <article class="people-card">
          <div class="people-card-header">
            <h3>{{ person.name }}</h3>
            <span class="people-status people-status-{{ person.status_class }}">{{ person.status }}</span>
          </div>
          <p class="people-meta">{{ person.period }} · {{ person.role }}</p>
          <p>{{ person.topic }}</p>
          {% if person.cosupervision %}
            <p class="people-cosupervision">Co-supervised with {{ person.cosupervision }}.</p>
          {% endif %}
        </article>
      {% endfor %}
    </div>
  </section>

  <section class="people-section" aria-labelledby="recent-projects">
    <h2 id="recent-projects">Recent student projects</h2>
    <p class="people-section-intro">Selected MSc and BSc projects completed or undertaken in 2026.</p>
    <div class="people-project-grid">
      {% for person in site.data.people.recent_projects %}
        <article class="people-project">
          <h3>{{ person.name }}</h3>
          <p class="people-meta">{{ person.level }} · {{ person.institution }}</p>
          <p>{{ person.topic }}</p>
        </article>
      {% endfor %}
    </div>
  </section>

  <section class="people-section" aria-labelledby="phd-alumni">
    <h2 id="phd-alumni">PhD alumni</h2>
    <div class="people-table-wrap">
      <table class="people-table">
        <thead>
          <tr>
            <th scope="col">Name</th>
            <th scope="col">Year</th>
            <th scope="col">Research</th>
            <th scope="col">Supervision</th>
          </tr>
        </thead>
        <tbody>
          {% for person in site.data.people.phd_alumni %}
            <tr>
              <th scope="row">{{ person.name }}</th>
              <td>{{ person.year }}</td>
              <td>{{ person.topic }}</td>
              <td>{{ person.supervision }}</td>
            </tr>
          {% endfor %}
        </tbody>
      </table>
    </div>
  </section>

  <section class="people-section" aria-labelledby="former-team">
    <h2 id="former-team">Former team members</h2>
    <div class="people-project-grid">
      {% for person in site.data.people.former_team %}
        <article class="people-project">
          <h3>{{ person.name }}</h3>
          <p class="people-meta">{{ person.period }} · {{ person.role }}</p>
          <p>{{ person.topic }}</p>
        </article>
      {% endfor %}
    </div>
  </section>

  <section class="people-section" aria-labelledby="student-archive">
    <h2 id="student-archive">Student project archive</h2>
    <details class="people-archive">
      <summary>View MSc, BSc, and engineering projects since 2017</summary>
      <div class="people-table-wrap">
        <table class="people-table people-table-archive">
          <thead>
            <tr>
              <th scope="col">Name</th>
              <th scope="col">Programme</th>
              <th scope="col">Research project</th>
            </tr>
          </thead>
          <tbody>
            {% for person in site.data.people.student_archive %}
              <tr>
                <th scope="row">{{ person.name }}</th>
                <td>{{ person.level }}{% if person.institution %}<br><span class="people-institution">{{ person.institution }}</span>{% endif %}</td>
                <td>{{ person.topic }}</td>
              </tr>
            {% endfor %}
          </tbody>
        </table>
      </div>
    </details>
  </section>
</div>
