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

<!-- Roll credits -->
<div class="credits-container">
    <div class="credits">
        <div class="credits-item">
            <div class="title">✨ Thanks for watching! ✨</div>
        </div>        
        <div class="credits-item">
            <div class="name">Céline Kalbermatten</div>
            <div class="role">Director</div>
        </div>
        <div class="credits-item">
            <div class="name">Nadezhda Ilieva</div>
            <div class="role">Producer</div>
        </div>
        <div class="credits-item">
            <div class="name">Said Gürbüz</div>
            <div class="role">Writer</div>
        </div>
        <div class="credits-item">
            <div class="name">Jennifer Shan</div>
            <div class="role">Cinematographer</div>
        </div>
        <div class="credits-item">
            <div class="name">Can Berk Alakir</div>
            <div class="role">Editor</div>
        </div>
        <div class="credits-item">
            <div class="general">🎥 C1n3mada Studios 🎥</div>
            <div class="general">December 2024</div>
        </div>
        <!-- Add more items as needed -->
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