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

The plot reveals that the relationship between IMDb ratings and box office revenue varies slightly across genres but no genre shows a really strong connection. While some genres, such as Period Piece and Film Adaptation, exhibit slightly higher correlations with values around 0.3 to 0.4, the values remain modest overall. This suggests that, regardless of genre, even if ratings play a role in revenue, they are not a decisive factor. The findings remain consistent: ratings can help but their impact is not dramatic and there are other factors influencing the drive box office success.

---

### A new character enters: the role of votes in the rating-revenue connection

What if the number of votes a movie receives actually matters more than the ratings themselves? Perhaps more popular movies reach a wider audience and therefore attract more people. Let’s analyse this in a 3D view that includes ratings, the number of votes and the box office revenue.

<iframe src="/assets/plots/echo/3d_regression_plane.html" width="100%" height="600px"></iframe>

The 3D visualization reinforces a clear pattern: votes win the day. Movies with a higher number of votes tend to get more revenue, regardless of their IMDb rating. The surface trend shows that revenue primarily increases with the number of votes. Ratings clearly contribute less to the relationship. This suggests that the number of votes has a stronger influence on box office success than the quality represented by the ratings. Widespread audience attention seems to be more important for the revenue than high ratings alone.

---

### Clearing the view: density map for revealing patterns in the data

With thousands of points, it’s easy to get lost in the scatterplot noise. Let’s visualize the data using a density map that groups the points into bins, making patterns clearer. 

<iframe src="/assets/plots/echo/hexbin_regression_plane.html" width="100%" height="600px"></iframe>

The density map confirms the earlier findings: most movies cluster around mid-level ratings and moderate box office revenues. The colour gradient shows a concentration of movies in this range. The gentle slope of the regression confirms that the relationship between ratings and revenue is weak. 

---

### The final scene: bringing it all together

So, after all the analysis, what can be concluded?

After looking at all the plots, correlations, and regression lines, some takeaways can be drawn:
- Ratings and revenue are only slightly connected. A high IMDb rating doesn’t mean a movie will be a box office hit. There is a link but it’s weak.
- Genre also matters a little. For some genres, the connection between ratings and revenue is slightly stronger but overall, the genre doesn’t really change the story.
- The real star is popularity. When considering the number of votes a movie gets, it becomes clear that popularity has a much bigger role in box office success. Ratings themselves start to matter less.

In the end, IMDb rating is like a supporting actor. They play a role but they are not the main driver of success. Popularity, measured by the number of votes, often takes the centre stage. So, the next time you pick a movie because of its rating, remember: it’s probably the movie’s popularity, not just that number, that’s bringing in the big bucks.

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