# <p align="center"> The Battle of Neighborhoods</p>
### <p align="center"> Author: Jong Hoon Lee</p>


## 1. Introduction
<p align="justify">For people considering to move strange city, getting correct information about candidates they are in mind is the most important thing. </p>

<p align="justify">In this project, we can help people to make a good decision looking for best place to migrate.
The main goal of this project is to give them a chance to know their potential neighborhoods more deeply.
For this goal we need to explore and gather a real world data and anylize them to draw a best insight.</p>

<p align="justify">Recently, Machine Learning algorithms make it easier to creates solutions than traditional statistics.
In our case, we will use one of many Machine Learning algorithms known as K-Means algorithm 
that is used to find patterns in data in terms of similarity between samples like our case.</p>

<p align="justify">Foursquare is an American technology company whose location platform is the foundation of several business and consumer products.
We will use dataset of location data provided by 'Foursquare' website which is location platform company in America.</p>

### 1.1. Business Problem

<p align="justify">Regarding the purpose of this project we need to analyse and select best locations in the city of Seoul, Korea.
For this aim, where can we get the data, which Machine Learning algorithms play a best roll 
and how can we make it easy to allow people to choice best place to move?</p>

## 2. Data

<p align="justify">
For this project two datasets (a list of neighborhoods in Seoul, longitude and latitude coordinates) supposed to be merged is obtained.
After that, additional venues data that are within a radius of 500m is requested using the API provided by the Foursquare. </p>

* https://en.wikipedia.org/wiki/List_of_postal_codes_of_Canada:_M (a list of neighborhoods in Seoul)
* Geocoder Python package                                         (longitude and latitude coordinates)

<p align="justify">The similarities that will be determined based on the frequency of the categories found in the neighborhoods
play an important roll in helping people to make right decision whether to move in a particular neighborhood 
near the center of Seoul or not.</p>

## 3. Methodology

### 3.1. Preprocessing
<p align="justify">In order to fit the data we prepare to the model One Hot Encoding is used.</p>

<p align="justify">One hot encoding is a process by which categorical variables are converted into a form 
that could be provided to ML algorithms to do a better job in prediction.</p>

<p align="justify">After one hot encoding 0 indicates non existent while 1 indicates existent.</p>

<p align="justify">In our case, categorical integer features One Hot Encoding 1 means this category matches the venue and 0 means the opposite.</p>

### 3.2. Clustering
<p align="justify">To find similarities between neighborhoods 
one of the simplest and popular unsupervised machine learning algorithms called K-means clustering is implemented.</p>

<p align="justify">The goal of this algorithm is to find groups in the data, with the number of groups represented by the variable K. 
The algorithm works iteratively to assign each data point to one of K groups based on the features that are provided. 
Data points are clustered based on feature similarity.</p>

<p align="justify">The centroids of the K clusters, which can be used to label new data as well as 
labels for the training data (each data point is assigned to a single cluster)
is the results of the K-means clustering algorithm.</p>

<p align="justify">In general, there is no method for determining exact value of K, but an accurate estimate can be obtained using the following techniques.</p>

<p align="justify">One of the metrics that is commonly used to compare results across different values of K is the mean distance between data points 
and their cluster centroid. 
Since increasing the number of clusters will always reduce the distance to data points, increasing K will always decrease this metric, 
to the extreme of reaching zero when K is the same as the number of data points. 
Thus, this metric cannot be used as the sole target. 
Instead, mean distance to the centroid as a function of K is plotted and the "elbow point," where the rate of decrease sharply shifts, 
can be used to roughly determine K.</p>

<p align="justify">In our case, the elbow is found around 5. The MSE found below this number shows little changes rather than big ones.</p>

<p align="center">
  <img src="https://github.com/chockroach/Coursera_Capstone/blob/master/images/bar_chart2.png" width="600" title="hover text">
</p>

## 4. Results

<p align="justify">As a Result, Neighborhoods in Seoul is Categorized into 5 clusters based on the frequency of occurrence for venues.</p>

* cluster 1 represents neighborhoods mainly consist of Coffee Shop, Korean Restaurant, Bakery, Bunsik Restaurant, Fast Food Restaurant.
* cluster 2 represents neighborhoods mainly consist of Coffee Shop, Donut Shop, Bus Stop, Udon Restaurant, Korean Restaurant.
* cluster 3 represents neighborhoods mainly consist of Bakery, Bed & Breakfast, Buffet, Museum, Fast Food Restaurant.
* cluster 4 represents neighborhoods mainly consist of Korean Restaurant, Vietnamese Restaurant, Auto Workshop.
* cluster 5 represents neighborhoods mainly consist of Hotel, Bus Station, Mountain(Park),Supermarket, Noodle House .

<p align="justify">The result of clustering are visualized in the map below with different colors for each cluster.</p>
<p align="center">
  <img src="https://github.com/chockroach/Coursera_Capstone/blob/master/images/seoul_map.png" width="600" title="hover text">
</p>

## 5. Discussion

<p align="justify">Although the proximity in terms of similarity in each cluster does not guarantee the geographical one
it is enough to briefly guess where is the good place to live since we can assume that at least clustering algoritm we use 
is doing well when it comes to similarity prediction.</p>

<p align="justify">If there is one thing missing we don't have sufficient privilege of access to enough data through Foursquare API. 
In another research we could make use of paid account to obtain unlimited data and more meaningful results.</p>

## 6. Conclusion

<p align="justify">In this project, we have undergone a chain of processes including knowing the business problem, gathering and preparing the data 
,clustering data by performing machine learning algorithm called k-means.</p>

<p align="justify">Finally, anyone who wants to move to Seoul can refer to the final result to make a good decision on what place would be the best to live.</p>

<p align="justify">Let's think, if there is one who is looking for convenient place to live we can recommend Cluster 2 without hesitation
since the neighborhoods in Cluster 2 have got essential facilities for convenient life including Bus Stop as well as not scattered.</p>
