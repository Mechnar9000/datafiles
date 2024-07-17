Hi all, this is my analytics portfolio right now. Please take a look at my work. 

#**Project 1: Bivariate choropleth**

[Link to source code](https://github.com/Mechnar9000/datafiles/blob/main/UK%20election%20results%20choropleths.ipynb)

This was made by joining two sources of electoral data (from the 2016 referendum on the UK's membership of the EU and from the 2017 UK general election) with a UK electoral constituency geojson file. The colouring indicates both the quartile of support for leave and the quartile of support for the Conservative party or UKIP. This allows us to synthesize the data from two different choropleths into one visualization. Using quartiles provides richer insight into the political landscape of the United Kingdom, allowing us to identify Labour-supporting regions that were in favour of Brexit as well as Conservative voting areas that were in favour of remaining within the European Union. 

![alt text](https://raw.githubusercontent.com/Mechnar9000/datafiles/main/bivariate_choropleth.jpg)

Insight from data: 

Reading the bivariate choropleth, it is clear regions to the north, west, and south of London leant towards the Conservatives or UKIP, but levels of support for leaving the EU were low. Meanwhile, regions to the east of London, as well as the East Midlands, both supported the Conservative/UKIP parties and leaving the EU. Regions in the north of England (around Manchester, Liverpool and West Yorkshire) as well as South Wales showed higher levels of support for leaving the EU but low levels of support for Conservatives/UKIP. Areas such as most of Scotland and Northern Ireland supported neither Conservative/UKIP parties nor leaving the EU. Ultimately, the visualization demonstrates that the vote to leave the European Union did not follow the traditional left-right party divisions within the United Kingdom. 

The visualizations of the data sources that are synthesized above can be seen below:

The first choropleth shows the proportion of voters who voted to leave in the 2016 election:

![alt text](https://raw.githubusercontent.com/Mechnar9000/datafiles/main/leave_voting.jpg)

The second choropleth shows the proportion of the electorate who voted for either the Conservative party or the UKIP party in the 2017 election. 

![alt text](https://raw.githubusercontent.com/Mechnar9000/datafiles/main/conservative_ukip_support.jpg)

Please note that, by tradition, the constituency that is held by the speaker of the House of Commons is not contested by the major parties. It has therefore been excluded from the data.

Finally, I show my own choropleth of regions where support for leaving the European Union exceeded 50%: 

![alt text](https://raw.githubusercontent.com/Mechnar9000/datafiles/main/majority_support.jpg)

#**Project 2: Distribution and frequency of German petrol stations at different postcode resolutions**

[Link to source code](https://github.com/Mechnar9000/datafiles/blob/main/Choropleth%20of%20German%20Petrol%20Stations.ipynb)

Germany's postcode system has the interesting characteristic of decreasing in regional resolution when the 5-digit postcode is truncated. This means that by using only the first n digits of the postcode, we can investigate more coarse-grained solutions, resulting in a deeper understanding of how they are distributed. 

**Full 5-digit resolution:**

This choropleth seems to have a resolution that is too fine-grained to make sense of. 

![alt text](https://github.com/Mechnar9000/datafiles/blob/main/5-digit.jpg)

**3-digit resolution:**

This choropleth appears show more interesting patterns. For example, a north-west to south-east coridor where petrol stations are more frequent. However, we must also consider that not all postcode regions are of equal geographic size in Germany, following population density, so the size of the regions in sparsely populated areas may be affecting this.  

![alt text](https://github.com/Mechnar9000/datafiles/blob/main/3-digit.jpg)

**2-digit resolution:**

This evenly more coarsely grained resolution seems to confirm the existence of the NW-SE corridor. It also shows the high frequency of petrol stations near the Benelux regions, which is perhaps due to high demand from trucks travelling from the Benelux ports into and out of Germany. 

![alt text](https://github.com/Mechnar9000/datafiles/blob/main/2-digit.jpg)




