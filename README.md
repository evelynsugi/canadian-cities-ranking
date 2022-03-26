# The Best Canadian City To Live In, Financially


## Introduction

Getting a job and figuring out where to live is one of the major routes for most university graduates. For international students studying in Canada, who usually do not have a permanent home, choosing their next home may be challenging as they may be unfamiliar with the country. In choosing where to live, two essential things to consider are the cost of living and salary information of that location. Thus, to help international students in deciding where to live in Canada, I scraped cost of living and salary information across cities in Canada and built a scoring system to rank which city is the best to live in financially.


## Background

There is an abundance of information available on the internet regarding the cost of living and salary information of cities in Canada. Despite the availability of information, collecting, reviewing, and comparing that information can be challenging and time-consuming. This project aims to gather that information automatically, analyze it, and present rankings of cities based on their scores on cost of living and salary. According to this ranking information, the decision maker can then choose the best city in Canada to live in based on its financial feasibility.


## Methodology

In order to gather cost of living and salary information across cities in Canada, data was scraped from numbeo.com, which is one of the world's largest cost of living database. This part was done in Python using the ‘requests’ library to request data from a specified URL, and the ‘BeautifulSoup’ library which is used to parse the HTML response. The result is then stored in a data frame (with cities along the rows and cost of food, apartment, salary, etc. along the columns) and later converted to a csv for further analysis in R. In R, Principal Component Analysis (PCA) was used to come up with a scoring system for the cities. PCA works by transforming the original variables (there are 53 variables in the original data) into a set of new variables where most of the variation in the data are contained within the first few new variables or principal components. The principal components are linear combinations of the original variables where the coefficients are often called loadings. Therefore, the principal components can be interpreted in terms of which variables have the highest loading magnitude. Lastly, the scores for each city are obtained by multiplying the original variables with the loadings.


## Results

The result from PCA’s scree plot suggest to retain 4 out of 53 components. Based on few of the highest magnitude of loadings of the original variables, the first, second, and third principal components can be roughly interpreted as scores for price of accommodation, groceries, and lifestyle of each city respectively. I can then rank the cities based on these scores and present the top five cities with the best scores for each component. The rank of cost of living of each city along with the salary ranking of each city can hopefully help the decision maker choose which city they think is the best place to live in financially.


## Conclusion

There is a lot of time and consideration involved in making a major decision like deciding where to live. Living expenses and salary are two essential financial considerations. This project helps the decision-maker saves time and effort by gathering information automatically and narrowing down the options into a few top ranked cities to consider for decision. Future versions of the project could include a user interface, such as a dashboard, that lets the user enter a list of cities they want the model to analyze. By doing so, the project can scale to include cities around the world instead of just Canadian cities.
