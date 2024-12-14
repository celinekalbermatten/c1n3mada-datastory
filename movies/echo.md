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

Ever wondered if a high IMDb rating truly translates into bigger box office bucks? Ratings often guide our viewing choices. A well-rated film draws us in, while a poorly rated one might push us away. But do higher scores actually mean more money? In the movie Echo, you explore the connection between IMDb ratings and a movie’s financial success - digging into whether there’s more to it than just the number on the screen.

---

### Setting the scene

Before linking ratings to revenue, it’s important to get a clear idea of the dataset. It covers a wide range of movies each categorized by genre, IMDb rating, and inflation-adjusted box office earnings. 

Let’s first explore the genre landscape. What are the most common genres? Different genres attract different audiences, and this might play a role in how much ratings actually impact financial success.

<iframe src="/assets/plots/echo/num_movies_per_genre.html" width="100%" height="600px"></iframe>

The bar chart illustrates the number of movies per genre in the dataset. Drama emerges clearly as the most common genre, with over 4’200 movies. The second most common genre is Comedy, which has nearly 3’000 movies. Thriller and Romance Film follow, with roughly 2’000 movies each. 

Genres like Action, Crime Fiction and Adventure are moderately represented, while categories such as Romantic Comedy, Romantic Drama and Horror have smaller counts, each under 1’000 movies. The least represented genres, including Mystery, Fantasy and Science Fiction have fewer than 700 entries.

This distribution highlights Drama's dominant presence, suggesting its broad appeal and versatility, whereas niche genres like World Cinema or Fantasy cater to more specific audiences. These disparities could influence how ratings impact financial success across genres.

---

### Rating and revenues: taking a closer look

The distribution of IMDb ratings raises an interesting question. Are most films clustering around a 6 or 7, or is the field wide open?

<iframe src="/assets/plots/echo/imdb_rating_distribution.html" width="100%" height="600px"></iframe>

The distribution of IMDb ratings reveals a clear trend. Most movies have ratings concentrated between 6 and 7, forming a noticeable peak in this range. This suggests that the majority of films receive moderate ratings. Ratings below 5 and above 8 are much less common. This suggests that movies rarely perform extremely poorly or receive exceptionally high ratings or that in such cases fewer people are providing ratings.

The distribution of box office revenues raises interest. Are movie earnings spread evenly across the spectrum or do a small number of blockbusters dominate the field?

<iframe src="/assets/plots/echo/box_office_revenue_distribution.html" width="100%" height="600px"></iframe>

The distribution of box office revenues shows a clear skew. Most movies cluster in a specific range with log-transformed revenues peaking around 7. This corresponds to moderate box office success and suggests that the majority of movies earn a relatively stable amount, neither flopping completely nor breaking records.

However, the long tail to the right indicates that a small number of movies achieve exceptionally high revenues and therefore skew the distribution. On the other hand, the left end of the curve shows a very small number of movies with extremely low earnings. This uneven spread highlights the disparity in box office success, where a few blockbusters dominate financially while most movies achieve more modest results.

---

### Ratings meet revenues: exploring the connection 

Now it’s time to bring everything together. On one axis are the IMDb ratings and on the other one the box office revenue (log-transformed for clarity). Does a higher rating always translate to bigger earnings? Or is the relationship more complicated than it seems? Let’s explore.

<iframe src="/assets/plots/echo/imdb_rating_vs_box_office_revenue.html" width="100%" height="600px"></iframe>

The plot is scattered and looks like distant stars rather than forming a tight cluster. While there is a slight upward trend, it’s not particularly strong. This suggests that higher IMDb ratings might provide some boost to box office revenue but they are not a guarantee for financial success. Even among movies with similar ratings, the revenues vary a lot. This highlights the complexity of factors that influence earnings beyond just audience or critic approval.

---

### Measuring the connection: correlation analysis 

Is this weak link real or could it just be a coincidence? Let’s check the correlation between the ratings, revenue and number of votes. Which of these factors are related and to what extent?

<iframe src="/assets/plots/echo/correlation_matrix.html" width="100%" height="600px"></iframe>

The correlation matrix shows how ratings, revenue and votes are connected. The strongest relationship is between the number of votes and the box office revenue with a moderate positive correlation of 0.50. This means that movies earning more revenue tend to attract more audience votes. Ratings show weaker connections with a 0.36 correlation to votes and a very weak correlation of 0.19 to revenue. This indicates that higher ratings might slightly help increase the number of votes and the financial success but they are not major drivers. Overall, the matrix shows that while some relationships exist, other factors likely have a stronger influence on these outcomes.

---

### Genre: the impact on the rating-revenue connection

Do certain genres rely more on ratings to drive revenue? Let’s take a closer look at the correlation between ratings and revenue across different genres to find out.

<iframe src="/assets/plots/echo/genre_correlation.html" width="100%" height="600px"></iframe>

Céline to doooooooooooooooooooo 

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