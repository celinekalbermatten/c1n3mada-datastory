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
        ✦ TONGUES ✦
    </div>
    <h2>How do the language and country of a movie influence its box office revenue?</h2>
    <!-- 
    <div class="small">
        🎥 A Production by <strong>C1n3mada Studios</strong>
    </div>
    -->
</div>

<!-- Content -->
<div class="content">
  <div class="text-custom">
      This film explores the importance of a movie's primary language and release country, as well as the correlation between these two aspects. Additionally, it shows whether movies with more than one original language achieve more success.
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