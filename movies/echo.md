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
    <div class="highlight">
        ✦ ECHO ✦
    </div>
    <h2>How does a movie’s IMDb rating relate to its box office success?</h2>
    <!-- 
    <div class="small">
        🎥 A Production by <strong>C1n3mada Studios</strong>
    </div>
    -->
</div>

<!-- Content -->
<div class="content">
  <div class="text-custom">
      <!-- added plots for your reference only rn -->
      <iframe src="/assets/plots/echo/num_movies_per_genre.html" width="100%" height="600px"></iframe>
      <iframe src="/assets/plots/echo/imdb_rating_vs_box_office_revenue.html" width="100%" height="600px"></iframe>
      <iframe src="/assets/plots/echo/imdb_rating_distribution.html" width="100%" height="600px"></iframe>
      <iframe src="/assets/plots/echo/hexbin_regression_plane.html" width="100%" height="600px"></iframe>
      <iframe src="/assets/plots/echo/genre_correlation.html" width="100%" height="600px"></iframe>
      <iframe src="/assets/plots/echo/correlation_matrix.html" width="100%" height="600px"></iframe>
      <iframe src="/assets/plots/echo/box_office_revenue_distribution.html" width="100%" height="600px"></iframe>
      <iframe src="/assets/plots/echo/3d_regression_plane.html" width="100%" height="600px"></iframe>
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