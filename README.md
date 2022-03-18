# Investigating-Fandango-Movie-Ratings

#### **Context:**  

This project is about analyzing an online movie rating aggregator called [Fandango](https://www.fandango.com/). In october 2015, a data journalist named Walt Hickey analyzed movie ratings data and found strong evidence to suggest that Fandango's rating system was biased. He published his analysis in this [article](https://fivethirtyeight.com/features/fandango-movies-ratings/). With a 5-star rating system (the minimum rating is 0 and the maximum rating is 5), Hickey found that there is a significant discrepancy between the number of stars displayed to users and the actual rating, whick he was able to find in the HTML of the page. he was able to find that:  
- The actual rating was almost always rounded up to the nearest half-star. For instance, a 4.1 movie would be rounded off to 4.5 stars, not to 4 stars.   
- In the case of 8% of the ratings analyzed, the rounding up was done to the nearest whole star. For instance, a 4.5 star would be rounded off to 5 stars.  
- For one movie, the rounding off went from 4 to 5 stars.

Frandango's officials replied that the biased rounding off was caused by a bug in their system rather than being intentional, and they promised to fix the bug as soon as possible.

#### **Goal:**  

Our goal is to analyze more recent movie ratings data to determine whether the has been any change in the Fandango's rating system after Hickey's analysis.  

#### **Dataset:**  

The best way to figure out whether there has been any change in Fandango's rating system after Hickey's analysis is to compare the system's characteristics before and after the analysis. To do that, I used two datasets:
- The first dataset is the one analyzed by Walt Hickey which he made available on [Github](https://github.com/fivethirtyeight/data/tree/master/fandango). This data is a csv file named "fandango_score_comparison.csv" and is used to analyze the characteristics of Fandango's rating system before his analysis. You can find the description of each column in the given link.
- The second dataset contains movie ratings data for movies released in 2016 and 2017. This data is named "movie_ratings_16_17.csv" and is used to analyze the rating system's characteristics after Hickey's analysis. Below is the descriptionof each column:

1. movie: the name of the movie.
2. year: the release year of the movie.
3. metascore: the Metacritic rating of the movie (the "metascore" - critic score).
4. imdb: the IMDB rating of the movie (user score).
5. tmeter: the Rotten Tomatoes rating of the movie (the "tomatometer" - critic score).
6. audience: the Rotten Tomatoes rating of the movie (user score).
7. fandango: the Fandango rating of the movie (user score).
8. n_metascore: the metascore normalized to a 0-5 scale.
9. n_imdb: 	the IMDB rating normalized to a 0-5 scale.
10. n_tmeter: the tomatometer normalized to a 0-5 scale.
11. n_audience: the Rotten Tomatoes user score normalized to a 0-5 scale.
12. nr_metascore: the metascore normalized to a 0-5 scale and rounded to the nearest 0.5.
13. nr_imdb: the IMDB rating normalized to a 0-5 scale and rounded to the nearest 0.5.
14. nr_tmeter: the tomatometer normalized to a 0-5 scale and rounded to the nearest 0.5.
15. nr_audience: the Rotten Tomatoes user score normalized to a 0-5 scale and rounded to the nearest 0.5.


**Note:** this code was written on RStudio.  
**Language:** R.  
**Packages:** readr, dplyr, stringr, ggplot2, tidyr.
