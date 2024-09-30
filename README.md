Hi all, this is my analytics portfolio right now. Please take a look at my work. 

If you want an overview of my notebook work and the kind of educational background I have, please look at [my notes from an introductory analytics modeling class in my master's program](https://github.com/Mechnar9000/datafiles/blob/main/Full%20notes%20on%20analytics%20modeling.ipynb)

#**Project 1: Hegelian retrieval-augmented generation**

[Link to code](https://github.com/Mechnar9000/datafiles/blob/main/Hegelian%20Retrieval%20Augmented%20Generation%20(RAG).ipynb)

This was a project I built provide a simple example of how a RAG system can be used to augment the output of a LLM (large language model) e.g. ChatGPT. I used "The Phenomenology of Spirit" by Hegel because it was an example of a large (and famously inscrutable) body of text. 

Three chunking approaches were experimented with:

1. Vectorization of whole sub-chapters (aphorisms)
2. Vectorization of sentences
3. Vectorization of sentences with n sentence padding either side of the retrieved

The model used for text embedding was "text-embedding-ada-002" which was famously used by the earlier ChatGPT models. This represents text as a 1536 element vector. This was accomplished using the ChatGPT API which handles most of the preprocessing. Nonetheless, some preprocessing of the raw text file was necessary to divide the text into chunks and remove some of the mess that resulted from scraping the data from a pdf file (llama was used for scraping).

The result of vectorization was m x 1536 matrix that represented the complete text where m is the number of chunks. 

A simple function was them implemented which takes a user question as text e.g. "What did Hegel say about spirit?" and converted it into the same embedding format. 

A cosine similiarity distance metric was then used to retrieve the top k most matching chunks and their indices by comparing the query embedding with the matrix. 

The raw text corresponding with the relevant vectors was then fed to the LLM as part of the user prompt alongside instructions to make use of the text when answering the question. 

With this model, I was able to demonstrate 3 key advantages of the RAG approach to AI tools:

1. The distance metric was successful in retrieving relevant information. The top k chunks returned generally contained information pertinent to the query where possible, meaning that cosine similiarity is an effective means to retrieve relevant information:

![alt text](https://raw.githubusercontent.com/Mechnar9000/datafiles/main/rag_output.jpg)

2. The instructions to the LLM alongside the relevant information meant that the RAG model avoided hallucination and would return "I don't know" if the returned chunks did not contain any relevant information while the basic LLM would return something speculative and potentially wrong:

![alt text](https://raw.githubusercontent.com/Mechnar9000/datafiles/main/rag_hallucination.jpg)

3. The RAG model was able to avoid factual mistakes by using the retrieved information. For example, when provided a query asking about a very niche reference to a metaphor in the work of Hegel, the RAG model response was confident, while the LLM incorrectly claimed that it was never explicitly discussed (but nonetheless made up an interpretation).

 ![alt text](https://raw.githubusercontent.com/Mechnar9000/datafiles/main/rag_mistake.jpg)

This toy model adequately demonstrates that key advantages of the RAG approach to any business looking to integrate AI into their practices and improve within-institution information search. A scaled and refined version of this approach would be able to vastly improve the quality of the responses an employee user of an LLM would obtain and offer protection against hallucinated responses that could lead incorrect business decisions. 













#**Project 2: Bivariate choropleth**

[Link to code](https://github.com/Mechnar9000/datafiles/blob/main/UK%20election%20results%20choropleths.ipynb)

This was made by joining two sources of electoral data (from the 2016 referendum on the UK's membership of the EU and from the 2017 UK general election) with a UK electoral constituency geojson file. The colouring indicates both the quartile of support for leave and the quartile of support for the Conservative party or UKIP. This allows us to synthesize the data from two different choropleths into one visualization. Using quartiles provides richer insight into the political landscape of the United Kingdom, allowing us to identify regions that were in favour of Brexit that do not vote for right-oriented parties as well as right-oriented voting areas that were in favour of remaining within the European Union. 

![alt text](https://raw.githubusercontent.com/Mechnar9000/datafiles/main/bivariate_choropleth.jpg)

Insight from data: 

Reading the bivariate choropleth, it is clear regions to the north, west, and south of London leant towards the Conservatives or UKIP, but levels of support for leaving the EU were low. Meanwhile, regions to the east of London, as well as the East Midlands, both supported the Conservative/UKIP parties and leaving the EU. Regions in the north of England (around Manchester, Liverpool and West Yorkshire) as well as South Wales showed higher levels of support for leaving the EU but low levels of support for right-oriented parties. Areas such as most of Scotland and Northern Ireland supported neither Conservative/UKIP parties nor leaving the EU.

The visualizations of the data sources that are synthesized above can be seen below:

The first choropleth shows the proportion of voters who voted to leave in the 2016 election:

![alt text](https://raw.githubusercontent.com/Mechnar9000/datafiles/main/leave_voting.jpg)

The second choropleth shows the proportion of the electorate who voted for either the Conservative party or the UKIP party in the 2017 election. 

![alt text](https://raw.githubusercontent.com/Mechnar9000/datafiles/main/conservative_ukip_support.jpg)

Please note that, by tradition, the constituency that is held by the speaker of the House of Commons (Buckingham) is not contested by the major parties in a general election. It has therefore been excluded from the choropleths that involve general election data. 

Finally, I show my own choropleth of regions where support for leaving the European Union exceeded 50%: 

![alt text](https://raw.githubusercontent.com/Mechnar9000/datafiles/main/majority_support.jpg)

#**Project 3: Distribution and frequency of petrol stations in Germany at different postcode resolutions**

[Link to code](https://github.com/Mechnar9000/datafiles/blob/main/Choropleth%20of%20German%20Petrol%20Stations.ipynb)

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




