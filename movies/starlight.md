---
layout: default
title: Money, Money, Movies
# permalink: /movies/echo
# hero_image: /assets/img/echo-hero.jpg
---

<!-- Glitter background -->
<div id="starshine">
    <div class="template shine"></div>
</div>

<!-- Title -->
<div class="sticky-banner">
  <!-- Back to Main Page Button -->
  <a href="../index.html" class="btn-main-page">
    🏠
    Back to Main Page
  </a>

  <div class="highlight">
    ✦ STARLIGHT ✦
    <h2>
      To what extent is a movie's box office revenue influenced by its director?
    </h2>
  </div>
  

  <!-- Previous and Next Movie Buttons -->
  <div class="movie-nav-buttons">
    <a href="shades.html" class="btn-movie-nav">
      <span class="nav-arrow">←</span>
      <span class="nav-text">Previous: Shades</span>
    </a>
    <a href="waves.html" class="btn-movie-nav">
      <span class="nav-text">Next: Waves</span>
      <span class="nav-arrow">→</span>
    </a>
  </div>
</div>

<!-- Content -->
<div class="content">
  <div class="text-custom">
    This film highlights which directors produce the most movies, which ones generate the highest total revenue and which ones achieve the best average revenue per movie.
  </div>
</div>


<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
<script>
  $(function () {
    var body = $("#starshine"),
      template = $(".template.shine"),
      stars = 500,
      sparkle = 20;

    var size = "small";
    var createStar = function () {
      template
        .clone()
        .removeAttr("id")
        .css({
          top: Math.random() * 100 + "%",
          left: Math.random() * 100 + "%",
          animationDelay: Math.random() * sparkle + "s"
        })
        .addClass(size)
        .appendTo(body);
    };

    for (var i = 0; i < stars; i++) {
      if (i % 2 === 0) {
        size = "small";
      } else if (i % 3 === 0) {
        size = "medium";
      } else {
        size = "large";
      }

      createStar();
    }
  });
</script>

<script>
  document.addEventListener("DOMContentLoaded", function () {
      const links = document.querySelectorAll("a"); // Select all links

      links.forEach(link => {
          link.addEventListener("click", function (e) {
              const href = this.getAttribute("href");
              if (href.startsWith("#") || href.includes("mailto:")) return;
              
              e.preventDefault(); // Prevent default navigation
              
              document.body.classList.add("fade-out");
              setTimeout(() => {
                  window.location.href = href; // Navigate after fade-out
              }, 300); // Match CSS duration
          });
      });

      // Fade-in effect when the page loads
      window.addEventListener("pageshow", (event) => {
          if (event.persisted) {
              document.body.classList.remove("fade-out");
          }
      });
  });
</script>