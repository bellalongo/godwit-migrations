# godwit-migrations

*[Read about my methods here!](https://github.com/bellalongo/godwit-migrations/blob/main/bellaLongo_finalPaper.pdf)*

or read this overview...

## Abstract
Through the use of the K Means algorithm, I prove that Marbled Godwits are among the many in the long list of animals affected by climate change. By clustering the nighttime temperatures of when the birds start their migration journey, I find that there is a direct correlation between these temperatures and when the birds decided to migrate either for a warmer climate or for breeding. These findings prove that not only changes in habitat affect animals, but also the change in climate in general can disrupt their migration patterns, causing them to migrate too early or too late.


## Dataset
The Alaskan Science Center equipped 9 of these godwits with solar-powered satellite transmitters while at their breeding grounds in Ugashik Bay in June 2008. The transmitters were programmed in a way to report data for 10 hours, and then shut off for the next 48 hours, resulting in over 10,000 locations in 2015 when the trackers were removed. This resulted in about 10,000 locations which I have used in my research. I also used the Meteostat API to obtain historical weather data for each departure, which is plotted below. 

![min_temp_plot](https://github.com/bellalongo/godwit-migrations/blob/main/plots/min_temp_plot.png?raw=true)

## K Means
K Means is a machine learning algorithm with the purpose being clustering the data into a specified k clusters. The algorithm begins by randomly selecting k centroids within the dataset, but you can also initialize the centroids by hand. Iterating until a convergence criterion is met, each row of the dataset is iterated through where the euclidean distance between the row and each centroid is calculated. 

The row is added to the cluster whose centroid has the minimum of these distances. The centroids are then updated after iterating through every row, and the process is repeated until convergence. 

To find the best 2 clusters, I created a new data frame containing only the month in numeric form, and the average minimum temperature for that month, which was obtained from the Marbled Godwit dataset described in the previous section. 

To plot the two clusters, I used a 2D density plot graph which displayed the data in a manner that clearly showed the relationship between month and temperature, without the distracting overplotting that comes with a simple scatter plot. 

![min_temp_plot](https://github.com/bellalongo/godwit-migrations/blob/main/plots/kmeans.png?raw=true)

