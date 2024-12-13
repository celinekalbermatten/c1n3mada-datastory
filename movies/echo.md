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
    ✦ ECHO ✦
    <h2>
      How does a movie’s IMDb rating relate to its box office success?
    </h2>
  </div>
  

  <!-- Previous and Next Movie Buttons -->
  <div class="movie-nav-buttons">
    <a href="./tongues.html" class="btn-movie-nav">
      <span class="nav-text">Next: Tongues</span>
      <span class="nav-arrow">→</span>
    </a>
  </div>
</div>

<!-- Content -->
<div class="content" markdown="1">
  <div class="text-custom" markdown="1">

**Ever wondered if a high IMDb rating truly translates into bigger box office bucks?** Ratings often guide our viewing choices. A well-rated film draws us in, while a poorly rated one might push us away. But do these stellar scores actually mean more money? In **Movie 1: Echo**, we look at the relationship between IMDb ratings and a film’s financial success—peeking behind the curtain to see if there's more at play than just the number after the decimal.

---

### **Setting the Scene**

Before linking ratings to revenue, let's understand our dataset. It spans numerous films, each tagged with genres, IMDb ratings, and inflation-adjusted box office earnings. One of our first steps: checking out the genre landscape.

**Which genres are most common?** Different genres attract different audiences, and this could influence how much ratings matter for revenue.

<iframe src="/assets/plots/echo/num_movies_per_genre.html" width="100%" height="600px"></iframe>

Drama, action, comedy... Some genres dominate, potentially affecting the rating–revenue link.

---

### Ratings & Revenues: Taking a Closer Look

**IMDb Ratings Distribution:** Are most films hovering around a 6 or 7, or is the field wide open?

<iframe src="/assets/plots/echo/imdb_rating_distribution.html" width="100%" height="600px"></iframe>

We find a cozy cluster in the mid-range, with fewer extremes.

**Box Office Revenue Distribution:** Movie earnings are wildly uneven. Some flicks barely recoup costs, others skyrocket to astronomical figures.

<iframe src="/assets/plots/echo/box_office_revenue_distribution.html" width="100%" height="600px"></iframe>

Taking the log of revenue helps even out the scale, making patterns clearer.

---

### Meeting in the Middle: Rating vs. Revenue

Now, let’s put them together: IMDb rating on one axis, (log) revenue on the other, and see if there's a strong bond.

<iframe src="/assets/plots/echo/imdb_rating_vs_box_office_revenue.html" width="100%" height="600px"></iframe>

It looks scattered—more like distant stars than a tight cluster. There's a slight upward tilt, but not a strong one. Higher ratings may help a bit, but they don’t guarantee a money shower.

---

### Measuring the Connection: Correlation

Is this mild link real or just a coincidence? We check correlation, a number that tells us if two variables move together.

<iframe src="/assets/plots/echo/correlation_matrix.html" width="100%" height="600px"></iframe>

The correlation is modestly positive (around 0.19). So yes, rating and revenue have a friendly handshake, not a passionate embrace.

---

### Genre: Does It Make a Difference?

Could certain genres care more about ratings when it comes to raking in revenue? We checked the correlation by genre:

<iframe src="/assets/plots/echo/genre_correlation.html" width="100%" height="600px"></iframe>

Some genres show a slightly stronger connection than others, but no genre changes the game entirely. The story remains: ratings help, but not dramatically.

---

### A New Character Enters: Popularity (Number of Votes)

What if popularity (captured by the number of votes a film receives) matters more than the rating itself? After all, being widely talked about might drive more people to buy tickets.

When we add the number of votes into our model, it turns out **popularity dwarfs rating as a revenue predictor**. In fact, once we factor in votes, rating’s influence shrinks dramatically.

Check out a 3D view of ratings, votes, and revenue:

<iframe src="/assets/plots/echo/3d_regression_plane.html" width="100%" height="600px"></iframe>

Votes win the day. Popular films (many votes) bring in more revenue, regardless of their rating.

---

### Clearing the View: Density Map

With thousands of points, it’s easy to get lost in scatterplot noise. A density map groups data points into bins, making patterns clearer.

<iframe src="/assets/plots/echo/hexbin_regression_plane.html" width="100%" height="600px"></iframe>

This confirms our findings: Most movies cluster around mid-level ratings and moderate revenues. The regression line is gentle, reinforcing that the rating–revenue relationship is weak.

---

### The Final Scene

So, after all the plots, correlations, and regression lines, what are the key takeaways?
- **Ratings & Revenue:** They are related, but only weakly. Having a great IMDb rating doesn’t guarantee a box office smash.
- **Genre Matters a Bit:** Some genres show a slightly stronger rating–revenue link, but none truly break the mold.
- **Popularity is King:** When we factor in how many votes a movie receives, we see that popularity plays a huge role in revenue. In fact, once popularity is considered, the rating itself becomes less important.

In the grand production of movie success, IMDb ratings are just a supporting actor, while sheer popularity often takes the lead role. So next time you pick a movie based on its rating, remember: it might be popular appeal, not just that shiny number, bringing in the big bucks.

  </div>

  <!-- add nice finished horizontal line here make it a bit thicker and bold -->
  <hr style="border-top: 3px solid #BFA86A;">

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