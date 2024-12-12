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
        ✦ STARLIGHT ✦
    </div>
    <h2>To what extent is a movie's box office revenue influenced by its director?</h2>
    <!-- 
    <div class="small">
        🎥 A Production by <strong>C1n3mada Studios</strong>
    </div>
    -->
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