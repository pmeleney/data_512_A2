# Purpose of Repository

This repository was created by Peter Meleney on October 17, 2019. It is meant to satisfy **Assignment A2: Bias in Data** for course DATA 512: Human Centered Data Science at the University of Washington Master's of Science in Data Science (MSDS) program.

# Purpose of Assignment
The stated objective of this assignment "is to explore the concept of bias through data on Wikipedia articles." [1]  I will analyze the coverage of politicians on Wikipedia and how the quality of coverage varies between countries and regions.  I will also write a reflection, focusing on how my understanding of bias in data improved through the completion of this project. 

# Data Provenance
The Wikidpedia politicians by country dataset is hosted on Figshare: https://figshare.com/articles/Untitled_Item/5513449, accessed October 13, 2019.  
I downloaded the population data from a file hosed on Canvas (A2: Bias in data/WPDS 2018 data.csv): https://canvas.uw.edu/courses/1319253/files/, accessed October 13, 2019.  These data reflect data drawn from the world population datasheet for 2018: https://www.prb.org/international/indicator/population/table/.  The ratings of various articles was recorded through the ORES API discussed in the relevant section.

# API Documentation
See Scores API section at: https://ores.wikimedia.org/

# Values of Fields
## Raw Data
### page_data
**page:** The title of the page referenced by the rev_id.
**country:** The Country where the politician in question is from.
**rev_id:** The revision id which identifies the page to be classified by ORES.

### WPDS_2018_data
**Geography:** The geography (Country or Region) for which the specified population applies.
**Population mid-2018 (millions):** The population of that region or country in millions as of mid 2018.

### Predictions
**rev_id:** the revision id which identifies the page classified by ORES.
**ORES_predicted class:** The predicted class of the page according to ORES API.  (LEVELS FA-Featured Article, GA-Good Article, B-B-class article, C C-class article, Stub-Stub-class article, Start-Start-class article).

## Clean_data
### population
**Region:** The region in which the country resides.
**Region Population mid-2018 (millions):** The population of the region in millions as of mid-2018.
**Country:** The country name
**Population mid-2018 (millions):** The population of the country in millions as of mid-2018.

### region
**Geography:** Region name.
**Population mid-2018 (millions):** Population of the region in millions as of mid-2018.

### rev_ids_not_in_predictions
**rev_id:** the revision id of pages not returned by the ORES API

### wikipedia
**page:** The title of the page referenced by the rev_id.
**country:** The Country where the politician in question is from.
**rev_id:** The revision id which identifies the page to be classified by ORES.
**Region:** The region in which the country resides.

### wp_wpds_politicians_by_country
**page:** The title of the page referenced by the rev_id.
**country:** The Country where the politician in question is from.
**ORES_predicted_class:** The predicted class of the page according to ORES API.  (LEVELS FA-Featured Article, GA-Good Article, B-B-class article, C C-class article, Stub-Stub-class article, Start-Start-class article).
**Region Population mid-2018 (millions):** Population of the region in millions as of mid-2018.
**Population mid-2018 (millions):** The population of the country in millions as of mid-2018.

# Special Considerations
I was not able to get the ORES package for python to work correctly on my windows machine, so I used the API instead.  I experienced extremely different speeds of the ORES API, in the middle of the day on October 16th, 2019 the API query ran for approximately 3 hours to return the specified data.  On the morning of October 17th, 2019, the same query ran in less than 10 minutes.

# References
[1] Morgan, Johnathan T. (2019, October 3)  Human Centered Data Science (Fall 2019)/Assignments.  Retrieved from: https://wiki.communitydata.science/Human_Centered_Data_Science_(Fall_2019)/Assignments, accessed on October 13, 2019.

[2] Morgan, Johnathan T. (2017, October 28) Bias on Wikipedia - Making ORES requests jtmorgan/data-512-a2.  Retrieved from: https://github.com/jtmorgan/data-512-a2/blob/master/NEW_hcds-a2-bias_demo.ipynb, accessed October 16, 2019.
