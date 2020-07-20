## 2. Data

<p align="justify">
For this project two datasets (a list of neighborhoods in Seoul, longitude and latitude coordinates) supposed to be merged is obtained.

To get longitude and latitude coordinates we use Geocoder Python package.
This package return longitude and latitude coordinates using defferent types of parameters that can be Administrative place names such as city, county, state, province, or country names
or Postal code, Street addresses and so on.
we will call the package inputing district names of Seoul, Korea.

After that, additional venues data that are within a radius of 500m is requested using the API provided by the Foursquare. </p>

* https://en.wikipedia.org/wiki/List_of_districts_of_Seoul (a list of neighborhoods in Seoul)
* Geocoder Python package                                  (longitude and latitude coordinates)

<p align="justify">The similarities that will be determined based on the frequency of the categories found in the neighborhoods
play an important roll in helping people to make right decision whether to move in a particular neighborhood 
near the center of Seoul or not.</p>