---
layout: default
title: Money, Money, Movies
---

<!-- Glitter background styling -->
<style>
#starshine {
  width: 100%;
  height: 100%;
  overflow: hidden;
  position: fixed;
  top: 0;
  left: 0;
  z-index: -1;
}

.template.shine {
  width: 2px;
  height: 2px;
  border-radius: 50%;
  background: #ffffff;
  box-shadow: 0 0 6px #fff, 0 0 10px #fff;
  position: absolute;
  opacity: 0.8;
  animation: shimmer 2s infinite;
}

@keyframes shimmer {
  0% { opacity: 0.8; }
  50% { opacity: 0.3; }
  100% { opacity: 0.8; }
}

.highlight {
  font-size: 1.5em;
  color: #fffa65;
  margin-bottom: 0.5em;
  font-weight: bold;
}

.text-custom {
  font-size: 1.1em;
  line-height: 1.6em;
  margin: 1em 0;
  color: #222;
  background-color: #f7f7f7;
  padding: 1em;
  border-radius: 5px;
}

.content {
  margin: 2em auto;
  max-width: 900px;
  padding: 1em;
}

h3 {
  margin-top: 2em;
  color: #333;
}

p {
  color: #444;
}

.small {
  font-size: 0.9em;
  color: #ccc;
}
</style>

<div id="starshine">
  <div class="template shine"></div>
</div>

<div class="sticky-banner">
  <div class="highlight">✦ WAVES ✦</div>
  <h2>How much is a movie’s box office revenue influenced by its release timing and duration?</h2>
  <!-- 
  <div class="small">
      🎥 A Production by <strong>C1n3mada Studios</strong>
  </div>
  -->
</div>

<div class="content">
  <div class="text-custom">
    This film provides insights into the influence of a movie’s release season on its success, and it also examines 
    how runtime and genre factor into the equation. Is that summer blockbuster formula actually backed by data? 
    And do longer films have a better shot at high revenue in certain seasons? Let’s find out.
  </div>

  <h3>Are all seasons created equal?</h3>
  <p>We begin with a broad overview. The histogram below shows the distribution of movie revenues. 
  As you hover over each bar, you can see the count of movies and the corresponding revenue range.</p>

  <div id="plot-revenue-distribution">
    <iframe src="{{ site.baseurl }}/assets/plots/waves/revenue_distribution.html" width="100%" height="500"></iframe> 
  </div>

  <p>Most movies cluster in the lower-revenue range, yet a handful of outliers achieve extraordinary earnings. 
  But how is this distribution influenced by the season of release?</p>

  <h3>Seasonal Patterns</h3>

  <div id="plot-season-revenue-bar">
    <iframe src="{{ site.baseurl }}/assets/plots/waves/season_revenue_bar.html" width="100%" height="500"></iframe> 
  </div>

  <p>Here, we may observe that certain seasons stand out. Perhaps summer shows higher average revenues, or maybe another season surprises us. Let's also observe the movie revenue distribution by season:</p>

  <div id="plot-season-revenue">
    <iframe src="{{ site.baseurl }}/assets/plots/waves/boxplot_season.html" width="100%" height="500"></iframe> 
  </div>

  <p>We observe that summer is the dominating season in revenue. However, although there are outliers in all of the seasons, winter does not seem like the best time to release a movie. But does runtime also play a part in these seasonal success stories?</p>

  <h3>Runtime vs. Revenue: A Seasonal Perspective</h3>
  <p>Let's explore the relationship between runtime and revenue across different seasons. 
  Use the legend on the side to select a season and observe how the correlation is:</p>

  <div id="plot-runtime-vs-revenue">
    <iframe src="{{ site.baseurl }}/assets/plots/waves/runtime_revenue_scatter.html" width="100%" height="500"></iframe> 
  </div>

  <p>In some seasons, longer films might earn more, while in others, runtime seems less important. For this plot, the general observation is the revenue increases with longer runtime, however it is not a strong relation.</p>

  <h3>Genre Effects</h3>
  <p>Different genres may have seasonal sweet spots. Select a genre to observe how its average revenue shifts by season:</p>

  <div id="plot-genre-season-heatmap">
    <iframe src="{{ site.baseurl }}/assets/plots/waves/genre_season_heatmap.html" width="100%" height="500"></iframe> 
  </div>

  <p>As you hover over the cells/bars, you may discover that certain genres thrive in spring times, 
  while others peak in fall or winter. The interplay of genre, season, and runtime shapes box office performance.</p>

  <h3>Day-of-Week and Year Patterns</h3>
  <p>Season isn’t the only timing factor. Release day of the week can influence revenue too. Check out the chart below 
  to see if movies released on Fridays or weekends tend to make more money on average:</p>

  <div id="plot-day-of-week">
    <iframe src="{{ site.baseurl }}/assets/plots/waves/dayofweek_revenue.html" width="100%" height="500"></iframe> 
  </div>

  <p>Notice any patterns? Best revenues were observed in movies released on Mondays and Wednesdays! But how about the release year?</p>

  <div id="plot-year">
    <iframe src="{{ site.baseurl }}/assets/plots/waves/genre_popularity_over_time.html" width="100%" height="500"></iframe> 
  </div>

  <p>Drama and Comedy appear as the most consistently popular genres, especially in recent decades. Genres like Action/Adventure and Romance Film gain prominence later, particularly in the latter half of the 20th century.</p>

</div>

<!-- jQuery for star animation (optional if you already included) -->
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
