<!-- ## Ballon D'Or Analysis -->

## Project Intro

The Ballon D'or is the biggest award in international soccer. Every winter, it is awarded to the overall "best" player in the world. This year's award was given on November 29, and coincidentally, around then I learned about clustering in my master's program. When we talked about k-means clustering, I wondered if the algorithm could tell between the "types" of soccer players.

For this project, I took data from FBRef, a website with all kinds of per-match data on soccer players, on each of the 30 nominees for the 2021 Ballon D'Or. Then, I used R, Python, and Tableau to restructure, analyze, and visualize the data. A repository with all my code and data can be found <a href="https://github.com/jcmeulle/ballon_d-or_analysis"> here. </a>

I clustered the players with k-means clustering so I could get a few groups of players that made sense in a soccer context before profiling them by these groups.

## Clustering

To actually cluster the players, I used k-means on normalized data. I tried some different numbers of clusters and looked at them in terms of soccer sense and mathematical sense. 6 clusters ended up making sense both soccer-wise and by the gap statistic!

Here's how the clusters look after plotting them in Tableau:

<iframe seamless frameborder="0" src="https://public.tableau.com/views/fbclust/Sheet2?:embed=yes&:display_count=yes&:showVizHome=no" width = '100%' height = '600'></iframe> 

The principal components cover about 76.8% of the variation in the data, so this visual is a fairly accurate representation of where players lie in relation to each other. These clusters were also surprisingly good - I was worried about their ability to separate wingers from more "Number 10" types of players who play in the middle of the field more often. I was also a little bit surprised to see Messi way up in the top right corner, but he did win the award.

Now that we have the clusters, we can look at some of the characteristics for each group.

## Profiling

I made radar charts for each group and plotted their average Assists, Aerials Won, Progressive Carries, Non-Penalty Goals, Interceptions, and Tackles. I thought that these variables would help show the differences between players more effectively than just the PCA clustering plot. Each variable was standardized from 0 to 1 to keep the axes consistent.

First, we can look into what makes the Attacking Midfielders and the Transcendent Stars different, since they were most similar to each other.

<div class="box">
  <iframe src="//plotly.com/~jcmeulle/24.embed" frameborder="0" scrolling="no" width="50%" height="512" align="left"> </iframe>
</div>

<div class="box">
  <iframe src="//plotly.com/~jcmeulle/33.embed" frameborder="0" scrolling="no" width="50%" height="512" align="right"></iframe>
</div>

Looking at these plots, we can see that the main difference is that the Transcendent Stars, made up entirely of Neymar and Messi, had way more progressive carries. Of course, they also scored significantly more goals. This shows that Messi and Neymar differentiate themselves by carrying the ball and scoring more while also assisting their teammates as much as the world's other great playmakers.

Next, let's look at Tricky Attackers vs. Target Men:

<div class="box">
  <iframe src="//plotly.com/~jcmeulle/35.embed" frameborder="0" scrolling="no" width="50%" height="512" align="left"> </iframe>
</div>

<div class="box">
  <iframe src="//plotly.com/~jcmeulle/31.embed" frameborder="0" scrolling="no" width="50%" height="512" align="right"></iframe>
</div>

Here, we see that both groups scored tons of goals and played basically no defense. The key differences here are slightly higher assists for the Tricky Attackers and much higher aerials won for the Target Men. These make complete sense - players like Lukaku and Haaland are much more known for their headers than people like Sterling and Salah.

Now, for our last comparison, we can look at the Deep-Lying Midfielders vs. the Defenders. Both should record decent defensive statistics, but there should also be some differences.

<div class="box">
  <iframe src="//plotly.com/~jcmeulle/29.embed" frameborder="0" scrolling="no" width="50%" height="512" align="left"> </iframe>
</div>

<div class="box">
  <iframe src="//plotly.com/~jcmeulle/27.embed" frameborder="0" scrolling="no" width="50%" height="512" align="right"></iframe>
</div>

The Defenders recorded a much higher rate of aerials won, which makes sense - big centerbacks make a living off of beating people to a ball in the air. The more surprising part of this is that the Defenders had less tackles and interceptions than the Deep-Lying Midfielders. My best guess on this one is that possession changes far more often in the midfield, where the ball pings around while midfielders aggressively press the other team. Defenders tend to play a little more passively because they're so close to their goal.

## Conclusion

