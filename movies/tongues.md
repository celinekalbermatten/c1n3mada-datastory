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
    ✦ TONGUES ✦
    <h2>
      How do the language and country of a movie influence its box office revenue?
    </h2>
  </div>
  

  <!-- Previous and Next Movie Buttons -->
  <div class="movie-nav-buttons">
    <a href="echo.html" class="btn-movie-nav">
      <span class="nav-arrow">←</span>
      <span class="nav-text">Previous: Echo</span>
    </a>
    <a href="shades.html" class="btn-movie-nav">
      <span class="nav-text">Next: Shades</span>
      <span class="nav-arrow">→</span>
    </a>
  </div>
</div>

<!-- Content -->
<div class="content" markdown="1">
  <div class="text-custom" markdown="1">

Does a movie’s language or country of release impact its box office success? Is a film in multiple languages more likely to reach a wider audience and bring in bigger numbers? In the movie Tongues, you explore how primary language, release country and multilingual films connect to box office success.

---

### Setting the scene

Before directly analysing the influence of the country and the language on the box office revenue, it is important to get an idea of the country and language distribution in the dataset. 

Let’s start by looking at the 10 most common countries out of the 105 total.

<iframe src="/assets/plots/tongues/top_10_movie_release_countries.html" width="100%" height="600px"></iframe>

The chart clearly shows that English-speaking countries dominate the list of top movie release countries. The United States of America leads with more than 7’500 released movies, which is almost seven times more than the second-highest release country, the United Kingdom. The remaining countries, such as France, Germany, and Canada show considerably lower numbers of movies. There is a strong presence of North America, Europe and parts of Asia, while South America and Africa are notably absent. 

What about the movie languages? Do the results align with the release country analysis? Let’s look at the 10 most common primary movie languages out of the 158 total.

<iframe src="/assets/plots/tongues/top_10_movie_languages.html" width="100%" height="600px"></iframe>

The chart shows that English strongly dominates as the primary language for movies, with more than 8’000 titles. It surpasses all other languages by far. French, Spanish, and German follow but with significantly fewer movies. The other languages, such as Italian, Korean, Japanese, Russian, Mandarin and Hindi show even smaller contributions to the total.

This pattern aligns with the earlier analysis of release countries, where English-speaking nations, particularly the United States, led the way. The dominance of English reflects its global reach and influence in the film industry. Other languages may have a more localised but still notable presence.

---

### TO DOOOO CÉLINEEEEE

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