## Project Intro

The Ballon D'or is the biggest award in international soccer. Every winter, it is awarded to the overall "best" player in the world. This year's award was given on November 29, and coincidentally, around then I learned about clustering in my master's program. When we talked about k-means clustering, I wondered if the algorithm could tell between the "types" of soccer players.

For this project, I took data from FBRef, a website with all kinds of per-match data on soccer players, on each of the 30 nominees for the 2021 Ballon D'Or. Then, I used R, Python, and Tableau to restructure, analyze, and visualize the data. A repository with all my code and data can be found at <a href="https://github.com/jcmeulle/ballon_d-or_analysis"> this link </a>

I clustered the players with k-means clustering so I could get a few groups of players that made sense in a soccer context before profiling them by these groups.

## Clustering

To actually cluster the players, I used k-means on normalized data. I tried some different numbers of clusters and looked at them in terms of soccer sense and mathematical sense. 6 clusters ended up making sense both soccer-wise and by the gap statistic!

Here's how the clusters look after plotting them in Tableau:

<iframe seamless frameborder="0" src="https://public.tableau.com/views/fbclust/Sheet2?:embed=yes&:display_count=yes&:showVizHome=no" width = '650' height = '450'></iframe> 
