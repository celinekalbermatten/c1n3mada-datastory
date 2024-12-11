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
<div style="
   background-color: #1a1a1a;
   padding: 40px; 
   border-radius: 20px; 
   text-align: center; 
   font-family: 'Garamond', serif; 
   box-shadow: 0 6px 18px rgba(0, 0, 0, 0.8); 
   color: white;
   margin-bottom: 40px;">
   <!-- add the margin that should come after the box here -->
   <div style="
      font-size: 1.2em; 
      color: #BFA86A; 
      font-weight: bold; 
      letter-spacing: 2px;">
      ✦ STARLIGHT ✦
   </div>
   <h2 style="
      font-size: 2em; 
      margin: 10px 0; 
      font-style: italic; 
      color: #D4C593;">
      To what extent is a movie's box office revenue influenced by its director?
   </h2>
   <div style="
      font-size: 1em; 
      color: #999; 
      margin-top: 20px;">
      🎥 A Production by <strong style="color: #E3D9B6;">C1n3mada Studios</strong>
   </div>
</div>


<div class="text-custom">
  This film highlights which directors produce the most movies, which ones generate the highest total revenue and which ones achieve the best average revenue per movie.
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