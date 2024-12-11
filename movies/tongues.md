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
      ✦ TONGUES ✦
   </div>
   <h2 style="
      font-size: 2em; 
      margin: 10px 0; 
      font-style: italic; 
      color: #D4C593;">
      How do the language and country of a movie influence its box office revenue?
   </h2>
   <div style="
      font-size: 1em; 
      color: #999; 
      margin-top: 20px;">
      🎥 A Production by <strong style="color: #E3D9B6;">C1n3mada Studios</strong>
   </div>
</div>


<div class="text-custom">
  This film explores the importance of a movie's primary language and release country, as well as the correlation between these two aspects. Additionally, it shows whether movies with more than one original language achieve more success.
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