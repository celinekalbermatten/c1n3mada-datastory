---
layout: default
# title: Introduction
title: Money, Money, Movies
# hero_image: /assets/img/title-hero.jpg
---

<!-- Glitter background -->
<div id="starshine">
  <div class="template shine"></div>
</div>

<!-- Title -->
<div style="
   background-color: #1a1a1a; 
   padding: 40px; 
   text-align: center; 
   font-family: 'Garamond', serif; 
   box-shadow: 0 6px 18px rgba(0, 0, 0, 0.8); 
   color: white;
   margin: -20px -20px 40px -20px;
   width: 100vw;
   position: relative;
   left: 50%;
   transform: translateX(-50%);">
  <!-- add the margin that should come after the box here -->
  <div style="
      font-size: 1.2em; 
      color: #BFA86A; 
      font-weight: bold; 
      letter-spacing: 2px;">
    ✦ A CINEMATIC EXPERIENCE ✦
  </div>
  <h1 style="
      font-size: 3.2em; 
      margin: 20px 0; 
      color: #E3D9B6; 
      font-weight: bold; 
      text-transform: uppercase;">
    Money, Money, Movies
  </h1>
  <h2 style="
      font-size: 2em; 
      margin: 10px 0; 
      font-style: italic; 
      color: #D4C593;">
    The Secrets of Movies' Box Office Success
  </h2>
  <div style="
      font-size: 1em; 
      color: #999; 
      margin-top: 20px;">
    🎥 A Production by <strong style="color: #E3D9B6;">C1n3mada Studios</strong>
  </div>
</div>

<div class="text-custom">
  <!-- <p>
    It’s time to take a break from whatever you’re doing and enjoy some movies. The lineup includes 6 movies, each telling its own story. Together, they provide insights into what influences a movie's box office revenue. How do factors like rating, language, country, genre, director or even the release season affect a movie’s financial success? Through the selected films you will get detailed insights in a fun and engaging way. Each factor is analysed individually, with overlapping analyses across several factors, all together providing a comprehensive understanding by the end. In addition to learning about the influencing factors you will also discover possible reasons, as the movies also include explanatory elements.
    </p> -->
  <p> Lights, camera, action! Get ready to dive into six handpicked movies that don’t just entertain—they reveal the
    secrets behind box office hits. What drives a film’s financial success? Is it the language, the genre, the director, or
    even the season it’s released? Each movie in this lineup holds a piece of the puzzle. As you watch, you’ll explore how factors like ratings,
    budget, country of origin, and more come together to shape success. These films don’t just show you the data—they
    bring it to life with engaging stories and fascinating connections. </p>
  <p> Sit back, hit play, and let the stars of cinema guide you through this fascinating journey. C1n3mada hopes that
    you are ready for this unique experience! 🎬 </p>

</div>


<!-- Movie grid -->
<div class="movie-grid">
  <a href="./movies/echo">
    <img src="./assets/img/echo.png" alt="Echo">
    <p><b>Echo</b></p>
  </a>
  <a href="./movies/tongues">
    <img src="./assets/img/tongues.png" alt="Tongues">
    <p><b>Tongues</b></p>
  </a>
  <a href="./movies/shades">
    <img src="./assets/img/shades.png" alt="Shades">
    <p><b>Shades</b></p>
  </a>
  <a href="./movies/starlight">
    <img src="./assets/img/starlight.png" alt="Starlight">
    <p><b>Starlight</b></p>
  </a>
  <a href="./movies/waves">
    <img src="./assets/img/waves.png" alt="Waves">
    <p><b>Waves</b></p>
  </a>
  <a href="./movies/treasure">
    <img src="./assets/img/treasure.png" alt="Treasure">
    <p><b>Treasure</b></p>
  </a>
  <!-- Add the other movies -->
</div>


<!-- Roll credits -->
<div class="credits-container">
  <div class="credits">
    <div class="credits-item">
      <div class="title">✦ ⭐️ 🎥 ★ Thanks for watching! ★ 🎬 ⭐️ ✦</div>
    </div>
    <div class="credits-item">
      <div class="name">Céline Kalbermatten</div>
      <div class="role">Master Student in Data Science</div>
    </div>
    <div class="credits-item">
      <div class="name">Nadezhda Ilieva</div>
      <div class="role">Master Student in Communication Systems</div>
    </div>
    <div class="credits-item">
      <div class="name">Said Gürbüz</div>
      <div class="role">Master Student in Computer Science</div>
    </div>
    <div class="credits-item">
      <div class="name">Jennifer Shan</div>
      <div class="role">Master Student in Neuro-X</div>
    </div>
    <div class="credits-item">
      <div class="name">Can Berk Alakir</div>
      <div class="role">Master Student in Computer Science</div>
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
<script>
  document.addEventListener("DOMContentLoaded", function () {
    const links = document.querySelectorAll(".movie-grid a"); // Select all movie links

    links.forEach(link => {
      link.addEventListener("click", function (e) {
        e.preventDefault(); // Prevent default navigation
        const href = this.getAttribute("href"); // Get the URL to navigate to

        // Add fade-out effect to the body
        document.body.classList.add("fade-out");

        // Wait for the animation to complete before navigating
        setTimeout(() => {
          window.location.href = href;
        }, 400); // Match the duration in CSS
      });
    });
  });
</script>