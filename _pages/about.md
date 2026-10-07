---
layout: about
title: about
permalink: /
profile:
  align: right
  image: profile_picture.jpg
  image_circular: false
  more_info: >
    <p class="profile-links">
      <a href="mailto:alexander.du@duke.edu" aria-label="Email" title="Email"><i class="fa-solid fa-envelope" aria-hidden="true"></i></a>
      <a class="cv-link" href="/assets/pdf/cv.pdf">CV</a>
      <a href="https://scholar.google.com/citations?user=s0vPxFkAAAAJ" aria-label="Google Scholar" title="Google Scholar"><i class="ai ai-google-scholar" aria-hidden="true"></i></a>
      <a href="https://github.com/alexanderzdu" aria-label="GitHub" title="GitHub"><i class="fa-brands fa-github" aria-hidden="true"></i></a>
      <a href="https://www.linkedin.com/in/alexander-du-a70b76217" aria-label="LinkedIn" title="LinkedIn"><i class="fa-brands fa-linkedin" aria-hidden="true"></i></a>
    </p>
selected_papers: false
social: false
announcements:
  enabled: false
latest_posts:
  enabled: false
---

<script>
  if (!localStorage.getItem("theme-default-set")) {
    if (localStorage.getItem("theme") === "system") setThemeSetting("light");
    localStorage.setItem("theme-default-set", "1");
  }

  const page = document.querySelector(".post");
  const themeButton = document.getElementById("light-toggle");
  if (page && themeButton) {
    const themeControl = document.createElement("div");
    themeControl.className = "page-theme-control";
    themeControl.appendChild(themeButton);
    page.prepend(themeControl);
  }
</script>

<style>
  body > header {
    display: none;
  }

  body.fixed-top-nav {
    padding-top: 0;
  }

  .post-header .desc:empty {
    display: none;
  }

  .post {
    position: relative;
  }

  .profile {
    width: min(100%, 185px);
  }

  .page-theme-control {
    position: absolute;
    top: 0;
    right: 0;
  }

  .page-theme-control #light-toggle {
    transform: none;
  }

  .profile .more-info .profile-links {
    display: flex;
    align-items: center;
    gap: 0.55rem;
    flex-wrap: wrap;
    font-family: Roboto, sans-serif;
    font-size: 1rem;
    margin-bottom: 0;
  }

  .profile .profile-links .cv-link {
    font-weight: 700;
  }

  .publications .links {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    gap: 0.3rem;
  }

  .publications .links .bibtex {
    order: -1;
  }

  @media (max-width: 575px) {
    .profile.float-right {
      float: none !important;
      margin: 0 0 1rem auto;
    }
  }
</style>

I am a third-year Ph.D. student in Computer Science at Duke University, advised by Prof. [Matthew Lentz](https://users.cs.duke.edu/~mlentz/) and Prof. [Danyang Zhuo](https://danyangzhuo.com). I received my B.S. in Computer Science and Mathematics from Duke in 2024.

My research interests broadly span machine learning systems. I currently focus on fine-grained GPU resource management. My previous work sits at the intersection of programming languages and machine learning, including code generation, proof synthesis, and verification of ML systems.

Outside of research, I play piano and violin, go rock climbing, and practice calligraphy.

<div style="clear: both;"></div>

## Publications

<div class="publications">
{% bibliography %}
</div>
