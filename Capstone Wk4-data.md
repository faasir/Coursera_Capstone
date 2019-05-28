
<center><h1>IBM Certified Data Scientist </h1>
<h1>Capstone Project </h1>
<h2>The Battle of Neighborhoods </h2> </center>

<h2> DATA Collection </h2>

<h3> 1) List of Indian restaurants in Boston Area</h3>
<br>
For the problem in hand, I need to find a list of existing Indian Restaurants serving in Boston, Somerville, Cambridge neighborhoods. Fortunatly, FourSquare offers API services to pull this type of information. So using FourSquare, a list is pulled. This data is in JASON format. This needs to be loaded into a dataframe and cleaned a little bit.

<br> <b>Here us the final dataframe</b>




| Name | Address | Latitude | Longitude |
| ---- | ---- | ---- | ---- |
|Surya Indian Express | 100 Cambridgeside Pl, Cambridge, MA | 42.368554 | -71.076184 |
|Surya Indian Kitchen N Catering | 114 Magazine St, Cambridge, MA | 42.359972 | -71.110151
|Indian Entrees | Winter St, Boston, MA | 42.355206 | -71.060087
| Divine Indian Food | 187 Devonshire, Boston, MA | 42.356182 | -71.057280
| Kashmir Indian Restaurant | 279 Newbury St, Boston, MA | 42.349252 | -71.083969
| Vivek's Indian Cottage | nan, |  Boston, MA | 42.353715 | -71.076118
| Tanjore Indian Restaurant | 18 Eliot St, Cambridge, MA | 42.372037 | -71.121696
| j.m.p. indian cuisine | 1095 Commonwealth Ave, Allston, MA | 42.352269 | -71.125373
| Mehak Halal - Pakistani & Indian Cuisine | 329 Sumner St, | East Boston, MA | 42.367132 | -71.036017
| Shanti Indian Cuisine | 7 Broad Canal Way, Cambridge, MA | 42.363270 | -71.082842
| Halal Indian Cuisine | 736 Huntington Ave, Boston, MA | 42.333734 | -71.105374
| Union Square Fine Indian Cuisine|63 Union Sq, Somerville, MA | 42.365751 | -71.098794
| Akbar Indian | 1250 Cambridge St, Cambridge, MA | 42.339323 | -71.079122
| Masala Square Indian Kitchen | 23 Union Sq, Somerville, MA | 42.379818 | -71.096690
| Vaisakhi Indian Kitchen | 157 Sutherland Rd, Brighton, MA | 42.341062 | -71.146821
| Mela Unique Indian Cafe N Grocery | 102 Washington St, Somerville, MA | 42.383580 | -71.084402
| Indian Cafe | 1665 Beacon St, Brookline, MA | 42.341866 | -71.136418
| Indian Club | 1755 Massachusetts Ave, Cambridge, MA | 42.378617 | -71.160520
| Mint Indian Eatery | 868 Broadway, Somerville, MA | 42.400773 | -71.117813
| Indian Restaurant | 3706 Washington St, Jamaica Plain, MA | 42.284932 | -71.129542
| India Pavilion | 17 Central Sq, Cambridge, MA | 42.365347 | -71.104777
| Rani Indian Bistro | 1353 Beacon St, Brookline, MA | 42.341750 | -71.122557
| Masala Authentic Indian & Nepali|  1121 Broadway, Somerville, MA | 42.403066 | -71.126842
| Chakra Indian Cuisine | 18 Pondview Pl, Tyngsboro, MA | 42.352597 | -71.155314
| Punjabi Dhaba | 225 Hampshire St, Cambridge, MA | 42.373808 | -71.101048
| Tikki Masala | 3706 Washington St, Jamaica Plain, MA | 42.300419 | -71.113069
| Taste of India | 519 Main St, Malden, MA | 42.427931 | -71.067329
| Bukhara | 701 Centre St, Jamaica Plain, MA | 42.311614 | -71.114466
| Kashish | 51 Leonard St, Belmont, MA | 42.397582 | -71.175280


Along with the targeted locations, the stake holders also provided a set of restaurant names and its ratings. This also will be used in analyzing the locations
<br>

| Name | Rating | 
 | ---- | ---- | 
 | Himalayan Kitchen | 4.7 | 
 | Vaisakhi Indian Kitchen | 4.6 | 
 | Punjabi Dhaba | 4.2 | 
 | Punjab Palace | 4.2 | 
 | Mehak Halal - Pakistani & Indian Cuisine | 4.1 | 


Here is a map of all Indian restaurants in Boston, Cambridge and Somerville area plotted. 

<div class="output_png output_subarea ">

<img src="https://github.com/faasir/Coursera_Capstone/blob/master/BOSIndRests.JPG">
</div>

<h3>2) Possible Restaurant addresses</h3>


```python

```

To further analyze the location, we  need 5 possible restaurant locations. Using Google maps API, the locations are determined and added to the dataframe. Here is the details.

| Address | Latitude | Longitude | 
 | ---- | ---- | ---- | 
 | Copley Place, Boston, MA | 42.347149 | -71.077828 | 
 | Prudential Center, Boston, MA | 42.347345 | -71.082503 | 
 | The Atrium, Cambridge, MA | 42.374167 | -71.120549 | 
 | Assembly Row, Somerville, MA | 42.393878 | -71.079055 | 
 | Faneuil Hall Marketplace, Boston, MA | 42.360250 | -71.054743 | 

<h3>3) Stake holders prefered restaurants and its rating</h3>

<h4>Nightlife Spot</h4>
1 "Nightlife Spot" venues are found within 750m of location

 | Name | 	Latitude | 	Longitude | 
 | ---- | ---- | ---- | 
 | HubSpot Beer Garden	 | 42.370123	 | -71.076663 | 

<h3> 4) Explore the neighborhood for eating, Shopping and Public transportation facility using the API offered by FourSquare</h3>

The key to be a successful restaurant is to have as much as foot traffic. Usually foot traffic is around food, entertainment and shopping areas with good transportation facilities like metro station and/or bus services. Using FourSquare, these places will be explored. We would also set a 750m distance. it is considered a reasonable distance to walk within 5 minutes.

<br>

<b>Following type of venue category will be used to search</b>

<h5>'Metro Station, Bus Stop, Nightlife Spot, Arts & Entertainment, Shop & Service, Food'</h5>

Using the ForuSquare API, the first restaurant in the restaurant dataframe is used to analyze the neighborhood which  is <b>'Surya Indian Express'</b>




<h4> Metro Stations </h4>

3 "Metro Station" venues are found within 750m of location

| Name	| Latitude | 	Longitude
| ----| ----| ---- |
| MBTA Lechmere Station| 	42.370929| 	-71.077212
| MBTA Community College Station | 	42.373732 | 	-71.069698
| MBTA Science Park / West End Station | 	42.366744 | 	-71.067782


<h4> Bust Stops </h4>
5 "Bus Stop" venues are found within 750m of location

 | Name | 	Latitude | 	Longitude | 
 | ---- | ---- | ---- | 
 | Super Duck Stop Havard | 	42.367180 | 	-71.076683 | 
 | Cambridgeside Galleria Shuttle Stop | 	42.366987 | 	-71.076557 | 
 | EZRide - Lechmere Stop | 	42.370476 | 	-71.077410 | 
  | MGH-ASR Shuttle Stop 3 | 	42.363880 | 	-71.067830 | 
 | MGH Shuttle Stop  1 | 	42.364081 | 	-71.067939 | 



<h4>Shop & Service</h4>
8 "Shop & Service" venues are found within 750m of location

 | Name | 	Latitude | 	Longitude | 
 | ---- | ---- | ---- | 
 | The Body Shop | 	42.368136 | 	-71.076238 | 
 | MOS Gift Shop | 	42.367420 | 	-71.070190 | 
 | Science Museum Gift Shop | 	42.367470 | 	-71.070202 | 
 | David And Luis barber shop | 	42.371382 | 	-71.083109 | 
 | Bill's Barber Shop | 	42.371717 | 	-71.083112 | 

<h4>Arts & Entertainment</h4>
1 "Arts & Entertainment" venues are found within 750m of location

| Name | 	Latitude | 	Longitude | 
| ---- | ---- | ---- | 
| Multicultural Arts Center | 	42.369867 | 	-71.079053 | 


<h4> 5)Methodology</h4>

By exploring the neighborhood using FourSquare API which provides details on number of venues of different categories around existing Indian restaurants.  This is captured in a table and analyzed. This data provides a baseline characteristics of existing Indian restaurants' neighborhood. With this data I can use <b>content based recommendation </b> technique to suggest the new solution 

The list of locations offered by Stakeholder's data will be combined with the matrix of data collected using neighborhood restaurants to become a weighted matrix of favorite cinema.

The weighted matrix can be applied on 5 target locations with venues information to generate a ranking result. The the top one on the ranking list can be recommended to the stakeholder.

<h5>Data Cleaning and preparation</h5>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>Address</th>
      <th>Latitude</th>
      <th>Longitude</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Surya Indian Express</td>
      <td>100 Cambridgeside Pl, Cambridge, MA</td>
      <td>42.368554</td>
      <td>-71.076184</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Surya Indian Kitchen N Catering</td>
      <td>114 Magazine St, Cambridge, MA</td>
      <td>42.359972</td>
      <td>-71.110151</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Indian Entrees</td>
      <td>Winter St, Boston, MA</td>
      <td>42.355206</td>
      <td>-71.060087</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Divine Indian Food</td>
      <td>187 Devonshire, Boston, MA</td>
      <td>42.356182</td>
      <td>-71.057280</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Kashmir Indian Restaurant</td>
      <td>279 Newbury St, Boston, MA</td>
      <td>42.349252</td>
      <td>-71.083969</td>
    </tr>
  </tbody>
</table>

with this data, I can now explore the neighborhood for the attractions surrounding each Indian restaurant. The process came up with about 833 entries. Here is a sample of the list, from the bottom of the list  
<table>
<tbody>
   <tr>
      <th>1</th>
      <td>Food</td>
      <td>42.314481</td>
      <td>-71.103612</td>
      <td>Amir's Natural Foods</td>
      <td>Bukhara</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Food</td>
      <td>42.314565</td>
      <td>-71.103266</td>
      <td>Laria Foods</td>
      <td>Bukhara</td>
    </tr>
    <tr>
      <th>0</th>
      <td>Bus Stop</td>
      <td>42.398381</td>
      <td>-71.174323</td>
      <td>MBTA Bus Stop | Belmont Center</td>
      <td>Kashish</td>
    </tr>
    <tr>
      <th>0</th>
      <td>Shop &amp; Service</td>
      <td>42.395194</td>
      <td>-71.172576</td>
      <td>Guarino's Barber Shop</td>
      <td>Kashish</td>
    </tr>
    <tr>
      <th>0</th>
      <td>Food</td>
      <td>42.395247</td>
      <td>-71.173282</td>
      <td>Functional Food</td>
      <td>Kashish</td>
    </tr>
  </tbody>
</table>

Here is a summary of venues in each category.  

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Shop &amp; Service</th>
      <td>289</td>
    </tr>
    <tr>
      <th>Food</th>
      <td>243</td>
    </tr>
    <tr>
      <th>Bus Stop</th>
      <td>137</td>
    </tr>
    <tr>
      <th>Metro Station</th>
      <td>93</td>
    </tr>
    <tr>
      <th>Arts &amp; Entertainment</th>
      <td>65</td>
    </tr>
    <tr>
      <th>Nightlife Spot</th>
      <td>6</td>
    </tr>
  </tbody>
</table>


Perform similar exercise on the target restaurent list. Here is the summary of venuese in each category. 

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Shop &amp; Service</th>
      <td>114</td>
    </tr>
    <tr>
      <th>Food</th>
      <td>100</td>
    </tr>
    <tr>
      <th>Bus Stop</th>
      <td>40</td>
    </tr>
    <tr>
      <th>Arts &amp; Entertainment</th>
      <td>25</td>
    </tr>
    <tr>
      <th>Metro Station</th>
      <td>22</td>
    </tr>
    <tr>
      <th>Nightlife Spot</th>
      <td>1</td>
    </tr>
  </tbody>
</table>

The category 'Nightlife spot' is present in only one location. So this category is dropped from analysis. After cleaning this there are 827 entries on the venue table and 301 entries in target venue table.

Here is the pivot table of targeted locations and numbers of  different categories.

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th>Category</th>
      <th>Arts &amp; Entertainment</th>
      <th>Bus Stop</th>
      <th>Food</th>
      <th>Metro Station</th>
      <th>Shop &amp; Service</th>
    </tr>
    <tr>
      <th>Location</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>L1</th>
      <td>14.0</td>
      <td>11.0</td>
      <td>30.0</td>
      <td>5.0</td>
      <td>30.0</td>
    </tr>
    <tr>
      <th>L2</th>
      <td>6.0</td>
      <td>8.0</td>
      <td>30.0</td>
      <td>6.0</td>
      <td>30.0</td>
    </tr>
    <tr>
      <th>L3</th>
      <td>0.0</td>
      <td>8.0</td>
      <td>8.0</td>
      <td>1.0</td>
      <td>19.0</td>
    </tr>
    <tr>
      <th>L4</th>
      <td>0.0</td>
      <td>2.0</td>
      <td>2.0</td>
      <td>1.0</td>
      <td>5.0</td>
    </tr>
    <tr>
      <th>L5</th>
      <td>5.0</td>
      <td>11.0</td>
      <td>30.0</td>
      <td>9.0</td>
      <td>30.0</td>
    </tr>
  </tbody>
</table>

Here is the share holder's favorite restaurants:

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>Rating</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Himalayan Kitchen</td>
      <td>4.7</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Vaisakhi Indian Kitchen</td>
      <td>4.6</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Punjabi Dhaba</td>
      <td>4.2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Punjab Palace</td>
      <td>4.2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Mehak Halal - Pakistani &amp; Indian Cuisine</td>
      <td>4.1</td>
    </tr>
  </tbody>
</table>

<h4>6) Data Analysis</h4>

Check the data type of values. Its all numeric.
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Data Type</th>
    </tr>
    <tr>
      <th>Category</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Arts &amp; Entertainment</th>
      <td>float64</td>
    </tr>
    <tr>
      <th>Bus Stop</th>
      <td>float64</td>
    </tr>
    <tr>
      <th>Food</th>
      <td>float64</td>
    </tr>
    <tr>
      <th>Metro Station</th>
      <td>float64</td>
    </tr>
    <tr>
      <th>Shop &amp; Service</th>
      <td>float64</td>
    </tr>
  </tbody>
</table>

<br>
Get the descriptive statistics of the venue table.
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th>Category</th>
      <th>Arts &amp; Entertainment</th>
      <th>Bus Stop</th>
      <th>Food</th>
      <th>Metro Station</th>
      <th>Shop &amp; Service</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>27.000000</td>
      <td>27.000000</td>
      <td>27.000000</td>
      <td>27.000000</td>
      <td>27.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>1.333333</td>
      <td>3.296296</td>
      <td>7.296296</td>
      <td>2.185185</td>
      <td>8.629630</td>
    </tr>
    <tr>
      <th>std</th>
      <td>2.586949</td>
      <td>3.719127</td>
      <td>9.530578</td>
      <td>3.508638</td>
      <td>8.970671</td>
    </tr>
    <tr>
      <th>min</th>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.500000</td>
      <td>0.000000</td>
      <td>2.500000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>0.000000</td>
      <td>3.000000</td>
      <td>2.000000</td>
      <td>0.000000</td>
      <td>7.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>1.000000</td>
      <td>5.000000</td>
      <td>8.500000</td>
      <td>3.000000</td>
      <td>9.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>8.000000</td>
      <td>14.000000</td>
      <td>28.000000</td>
      <td>10.000000</td>
      <td>28.000000</td>
    </tr>
  </tbody>
</table>

It is very unusual to have 10 Metro Stations around in one restaurant. It needed further investigation.  
Indian Entrees is one of the restaurants having 10 stations around it. Here is the listing of the venue table entries for Metro Station. 

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Category</th>
      <th>Latitude</th>
      <th>Longitude</th>
      <th>Name</th>
      <th>Rest Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2</th>
      <td>Metro Station</td>
      <td>42.355368</td>
      <td>-71.060215</td>
      <td>MBTA Downtown Crossing Station</td>
      <td>Indian Entrees</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Metro Station</td>
      <td>42.359605</td>
      <td>-71.059440</td>
      <td>MBTA Government Center Station</td>
      <td>Indian Entrees</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Metro Station</td>
      <td>42.353146</td>
      <td>-71.064470</td>
      <td>MBTA Boylston Street Station</td>
      <td>Indian Entrees</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Metro Station</td>
      <td>42.358321</td>
      <td>-71.057156</td>
      <td>MBTA State Street Station</td>
      <td>Indian Entrees</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Metro Station</td>
      <td>42.361270</td>
      <td>-71.062072</td>
      <td>MBTA Bowdoin Station</td>
      <td>Indian Entrees</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Metro Station</td>
      <td>42.352312</td>
      <td>-71.062741</td>
      <td>MBTA Chinatown Station</td>
      <td>Indian Entrees</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Metro Station</td>
      <td>42.349574</td>
      <td>-71.063716</td>
      <td>MBTA Tufts Medical Center Station</td>
      <td>Indian Entrees</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Metro Station</td>
      <td>42.359435</td>
      <td>-71.053193</td>
      <td>MBTA Aquarium Station</td>
      <td>Indian Entrees</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Metro Station</td>
      <td>42.359161</td>
      <td>-71.057979</td>
      <td>Mbta Bowdoin Station</td>
      <td>Indian Entrees</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Metro Station</td>
      <td>42.360510</td>
      <td>-71.065867</td>
      <td>State St Station</td>
      <td>Indian Entrees</td>
    </tr>
   </tbody>
 </table>
 
 <br>
 Further analysis shows that these station list are valid. In Boston, since there are multiple lines of subways have same station in different places, they are marked differently (usually prefixed with a subway line color. ex. 'Blue line State street' and etc.). Since each line serves different regions of Boston, these are valid stations; so lets leave it alone.

Now, plot the data distribution. Here is the graphs produced by matplotlibs:




<div class="output_png output_subarea ">

<img src="https://github.com/faasir/Coursera_Capstone/blob/master/DistributionOfProps.png">
</div>


```python

```

<p>The distribution of other variables are quite similar. Now check their Pearson Correlation</p>


<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th>Category</th>
      <th>Arts &amp; Entertainment</th>
      <th>Bus Stop</th>
      <th>Food</th>
      <th>Metro Station</th>
      <th>Shop &amp; Service</th>
    </tr>
    <tr>
      <th>Category</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Arts &amp; Entertainment</th>
      <td>1.000000</td>
      <td>0.636948</td>
      <td>0.757111</td>
      <td>0.395491</td>
      <td>0.754646</td>
    </tr>
    <tr>
      <th>Bus Stop</th>
      <td>0.636948</td>
      <td>1.000000</td>
      <td>0.852480</td>
      <td>0.328696</td>
      <td>0.661675</td>
    </tr>
    <tr>
      <th>Food</th>
      <td>0.757111</td>
      <td>0.852480</td>
      <td>1.000000</td>
      <td>0.365206</td>
      <td>0.824137</td>
    </tr>
    <tr>
      <th>Metro Station</th>
      <td>0.395491</td>
      <td>0.328696</td>
      <td>0.365206</td>
      <td>1.000000</td>
      <td>0.372522</td>
    </tr>
    <tr>
      <th>Shop &amp; Service</th>
      <td>0.754646</td>
      <td>0.661675</td>
      <td>0.824137</td>
      <td>0.372522</td>
      <td>1.000000</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>It seems that 'Bus Stop', 'Shop &amp; Service' and 'Metro Station' category are highly correlated.
<br>Find P-Value of the variables </br></p>
<p>By convention, when the p-value is:</p>
<p>&lt; 0.001 we say there is strong evidence that the correlation is significant,<br>
&lt; 0.05; there is moderate evidence that the correlation is significant,<br>
&lt; 0.1; there is weak evidence that the correlation is significant, and<br>
if &gt; 0.1; there is no evidence that the correlation is significant.<br></p>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Category</th>
      <th>Arts &amp; Entertainment</th>
      <th>Bus Stop</th>
      <th>Food</th>
      <th>Metro Station</th>
      <th>Shop &amp; Service</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Arts &amp; Entertainment</td>
      <td>strong</td>
      <td>strong</td>
      <td>strong</td>
      <td>moderate</td>
      <td>strong</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Bus Stop</td>
      <td>strong</td>
      <td>strong</td>
      <td>strong</td>
      <td>weak</td>
      <td>strong</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Food</td>
      <td>strong</td>
      <td>strong</td>
      <td>strong</td>
      <td>weak</td>
      <td>strong</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Metro Station</td>
      <td>moderate</td>
      <td>weak</td>
      <td>weak</td>
      <td>strong</td>
      <td>weak</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Shop &amp; Service</td>
      <td>strong</td>
      <td>strong</td>
      <td>strong</td>
      <td>weak</td>
      <td>strong</td>
    </tr>
  </tbody>
</table>

<br>
Correlation between 'Arts & Entertainment','Bus Stop', 'Food', 'Shop & Service' are statistically significant; and the relationship is positive.

Here is the share holder's favorite restaurants:

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>Rating</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Himalayan Kitchen</td>
      <td>4.7</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Vaisakhi Indian Kitchen</td>
      <td>4.6</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Punjabi Dhaba</td>
      <td>4.2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Punjab Palace</td>
      <td>4.2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Mehak Halal - Pakistani &amp; Indian Cuisine</td>
      <td>4.1</td>
    </tr>
  </tbody>
</table>

Here is the plot of all restaurants, including the targeted, stake holders' favorites. 


<img src="https://github.com/faasir/Coursera_Capstone/blob/master/Plot.RestLocations.JPG">

Most of all restaurants are closely located to main roads or near big shopping places or near big educational institutions. 


<h4> 7) Machine Learning </h4>

With these data handy, we will use the Content-Based recommendation system to predict the best location. The idea is to use stake holder's favorite restaurants and near by venues around it and their ratings. 

Normalized venue table and the first 5 rows of it, listed below:
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th>Category</th>
      <th>Arts &amp; Entertainment</th>
      <th>Bus Stop</th>
      <th>Food</th>
      <th>Metro Station</th>
      <th>Shop &amp; Service</th>
    </tr>
    <tr>
      <th>Rest Name</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Akbar Indian</th>
      <td>1.000</td>
      <td>0.428571</td>
      <td>0.464286</td>
      <td>0.2</td>
      <td>0.321429</td>
    </tr>
    <tr>
      <th>Bukhara</th>
      <td>0.000</td>
      <td>0.000000</td>
      <td>0.035714</td>
      <td>0.0</td>
      <td>0.250000</td>
    </tr>
    <tr>
      <th>Chakra Indian Cuisine</th>
      <td>0.000</td>
      <td>0.071429</td>
      <td>0.000000</td>
      <td>0.0</td>
      <td>0.107143</td>
    </tr>
    <tr>
      <th>Divine Indian Food</th>
      <td>0.625</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.0</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>Halal Indian Cuisine</th>
      <td>0.000</td>
      <td>0.000000</td>
      <td>0.035714</td>
      <td>0.5</td>
      <td>0.107143</td>
    </tr>
  </tbody>
</table>

Below is the normalized stake holder's favorites' table. Two entries were dropped, because of non-sufficient entries.   

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Arts &amp; Entertainment</th>
      <th>Bus Stop</th>
      <th>Food</th>
      <th>Metro Station</th>
      <th>Shop &amp; Service</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>0.000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.9</td>
      <td>0.035714</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0.125</td>
      <td>0.214286</td>
      <td>0.035714</td>
      <td>0.0</td>
      <td>0.178571</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0.125</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.0</td>
      <td>0.035714</td>
    </tr>
  </tbody>
</table>

Recommendation Component - Dot product to get the weight of rating on each category according to stakeholder's favourite list.


|Category|	Weighted Rating|
|----|----|
 | Arts & Entertainment | 4.766667 | 
 | Bus Stop|11.544828 | 
 | Food|11.251852 | 
 | Metro Station	 | 13.900000 | 
 | Shop & Service	 | 15.517857 | 

Recommendation List - With the stake holder's  profile and the complete list of the restaurants and their venues count in hand, weighted average of the target locations should give enough information to recommend a location to the stake holders. 
Here is the weighted average of the locations. 

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th>Location</th>
        <th>Name</th>
      <th>Latitude</th>
      <th>Longitude</th>
      <th>Rating</th>  
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>L1</td>
      <td>Vaisakhi Indian Kitchen</td>
      <td>42.341062</td>
      <td>-71.146821</td>
      <td>0.375140</td>
    </tr>
     <tr>
      <td>L2</td>
      <td>Punjabi Dhaba</td>
      <td>42.373808</td>
      <td>-71.101048</td>
    <td>0.398907</td>
    </tr>
    <tr>
      <td>L4</td>
      <td>Mehak Halal - Pakistani &amp; Indian Cuisine</td>
      <td>42.367132</td>
      <td>-71.036017</td>        
      <td>0.328762</td>
    </tr>

  </tbody>
</table>

<h4> 8)Results</h4>
Based of the weighter average of the locations compared to the list of restaurants provided by the stake holders, the best places to start the new restaurant is at a place like where <b>Punjabi Dhaba</b> is located.

So our recommendation is somewhat better than expected.



Each count of venues in Boston area is as below:

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th>Category</th>
      <th>Average Count</th>
    </tr>
  </thead>
  <tbody>
      <tr>
          <td>Arts &amp; Entertainment</td>
          <td>1.0</td>
      </tr>
      <tr>
          <td>Bus top</td>
           <td>3.0</td>
      </tr>
      <tr>
          <td>Food</td>
          <td>7.0</td>
      </tr>
      <tr>
      <td>Metro Station</td>
        <td>2.0</td>
      </tr>
      <tr>
          <td>Shop &amp; Service</td>   
      <td>9.0</td>
    </tr>
  </tbody>
</table>

Our recomended location has above average venues compared to overall Boston venues as shown below.


<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th>Category</th>
      <th>Average Count</th>
    </tr>
  </thead>
  <tbody>
      <tr>
          <td>Arts &amp; Entertainment</td>
          <td>2.0</td>
      </tr>
      <tr>
          <td>Bus top</td>
           <td>4.3</td>
      </tr>
      <tr>
          <td>Food</td>
          <td>12.0</td>
      </tr>
      <tr>
      <td>Metro Station</td>
        <td>4.0</td>
      </tr>
      <tr>
          <td>Shop &amp; Service</td>   
      <td>15.0</td>
    </tr>
  </tbody>
</table>



```python

```
