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
        ✦ SHADES ✦
    </div>
    <h2>How does a movie's genre impact its box office revenue?</h2>
    <!-- 
    <div class="small">
        🎥 A Production by <strong>C1n3mada Studios</strong>
    </div>
    -->
</div>

<!-- Content -->
<div class="content">
  <div class="text-custom">
    This film aims to provide an understanding of whether certain genres are associated with higher revenues and if the relationship between genre and revenue changes over time.
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