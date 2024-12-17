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
    ✦ STARLIGHT ✦
    <h2>
      To what extent is a movie's box office revenue influenced by its director?
    </h2>
  </div>

  <!-- Previous and Next Movie Buttons -->
  <div class="movie-nav-buttons">
    <a href="shades.html" class="btn-movie-nav">
      <span class="nav-arrow">←</span>
      <span class="nav-text">Previous: Shades</span>
    </a>
    <a href="waves.html" class="btn-movie-nav">
      <span class="nav-text">Next: Waves</span>
      <span class="nav-arrow">→</span>
    </a>
  </div>
</div>

<!-- Content -->
<div class="content" markdown="1">
  <div class="text-custom" markdown="1">
We often think of famous directors like **Steven Spielberg**, **Quentin Tarantino**, or **Martin Scorsese**. But how much does a director truly influence a movie's box office success? In the movie *Starlight*, we dive into the connection between directors and box office performance.

### What is the role of a director?

A director's role is to bring a script to life. They oversee the creative aspects of a film, including its visual style, tone, and the performances of the actors. A director is the key driving force in a movie's production, making crucial decisions that shape the final product. But who are the directors behind the highest-grossing movies?

<iframe src="{{ site.baseurl }}/assets/plots/starlight/log_max_box_office_revenue_over_time.html" width="100%" height="600px"></iframe>

Surprisingly, the leader here is **Victor Fleming** in 1939, who directed _Gone with the Wind_, one of the highest-grossing movies of all time. This may come as a surprise, as Fleming is less well-known than directors like **Steven Spielberg** or **James Cameron**. To explore further, let's examine some metrics that highlight a director's influence:

- The total box office revenue of all movies directed by a director,
- The number of movies directed.

<iframe src="{{ site.baseurl }}/assets/plots/starlight/top_15_directors_total_revenue.html" width="100%" height="600px"></iframe>

As expected, **Steven Spielberg** tops the list of directors with the highest total box office revenue, followed by **James Cameron** and **Peter Jackson**. But does being a successful director also mean directing more movies? Let’s take a look at the number of movies directed by each filmmaker.

<iframe src="{{ site.baseurl }}/assets/plots/starlight/top_15_directors_movie_count.html" width="100%" height="600px"></iframe>

Here we again see many well-known directors, such as **Steven Spielberg**, **Woody Allen**, and **Clint Eastwood**, who have directed numerous films. However, these static views don't clearly show how consistent these directors are over time. To better visualize this, let’s let them race! Here is an animated race chart showing the top 15 directors by cumulative box office revenue over time.

<iframe src="{{ site.baseurl }}/assets/plots/starlight/cumulative_revenue_director_top15_raceplot.html" width="100%" height="600px"></iframe>

This race reveals how some directors, such as **Spielberg**, take the lead later in time and dominate for long periods. However, in this race we are more looking at the success of the directors instead of movie success. To get another perspective, let’s look at the top 15 movies each year using a treemap.

<iframe src="{{ site.baseurl }}/assets/plots/starlight/slow_top_15_movie_revenue_by_director.html" width="100%" height="600px"></iframe>

This visualization shows that, in every years or mostly at least, a single movie dominates the box office revenue. Furthermore, some directors manage to place multiple movies in the top 15, further showcasing their consistent success. Now, let’s extend this concept and view the top 15 directors over time in a treemap format.

<iframe src="{{ site.baseurl }}/assets/plots/starlight/top_15_movie_director_treemap_over_time.html" width="100%" height="600px"></iframe>

This treemap reveals that once a director achieves significant success, they often remain at the top for long periods. While the leaders change over decades, successful directors maintain their influence for extended stretches of time.

### Conclusion

Through these visualizations, we can see that directors do play an important role in a movie's box office performance. Successful directors not only achieve significant revenues but also maintain their dominance over time. However, it is important to note that while the director is a critical factor, other elements—such as cast, marketing, and story—also contribute to a movie's success.

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
