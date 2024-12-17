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
    ✦ BUDGET ✦
    <h2>
      How does a movie's budget impact its box office revenue?
    </h2>
  </div>
  

  <!-- Previous and Next Movie Buttons -->
  <div class="movie-nav-buttons">
    <a href="./waves.html" class="btn-movie-nav">
      <span class="nav-arrow">←</span>
      <span class="nav-text">Previous: Waves</span>
    </a>
    <!-- add empty button for next movie as this is the last movie -->
    <a>
    </a>
  </div>
</div>

<!-- Content -->
<div class="content">
  <div class="text-custom">
    .
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
              
              // Ignore anchor links or mailto
              if (href.startsWith("#") || href.includes("mailto:")) return; 
              
              e.preventDefault(); // Prevent default navigation
              
              // Add the new modern transition class
              document.body.classList.add("page-exit");
              
              // Wait for the animation to complete before navigating
              setTimeout(() => {
                  window.location.href = href;
              }, 400); // Duration matches the CSS transition
          });
      });

      // Handle browser back/forward cache
      window.addEventListener("pageshow", (event) => {
          if (event.persisted) {
              document.body.classList.remove("page-exit");
          }
      });
  });
</script>