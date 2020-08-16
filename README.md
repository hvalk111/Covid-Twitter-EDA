# Project_5_Team
## COVID-19 Rates via Sentiment Analysis of Tweets
#### Lucas Dwyer, Henry Valk, and Margret Rubio-Keefer

## Problem Statement:
##### The COVID-19 response has been largely regional and state-based in nature. Some states have enacted strictly enforced stay-at-home policies, while others have provided guidelines. It would be worthwhile to compare the sentiment analysis of social media posts across geographic regions and compare them to  the local  the occurrences of the pandemic in those areas. Furthermore, it would be useful if any time series forecasting model based on social media sentinment analysis data.

## Datasets
##### Selected states (for data size purposes): NY, CA, TX, FL, GA
### [CORONAVIRUS (COVID-19) GEO-TAGGED TWEETS DATASET](https://ieee-dataport.org/open-access/coronavirus-covid-19-geo-tagged-tweets-dataset)
##### [Hydrator](https://github.com/DocNow/hydrator/releases/tag/v0.0.13) must be used to process the tweets.
This dataset was processed down to the daily mean sentinment by TextBlob in the form of polarity `TB_polarity` and subjectivity `TB_subjectivity`, indexed by day, for the five selected states.

### [COVID-19 Data Repository by the Center for Systems Science and Engineering (CSSE) at Johns Hopkins University](https://github.com/CSSEGISandData/COVID-19)
This dataset was processed down to the daily confirmed cases and daily confirmed deaths, indexed by day, for the five selected states.

## Models
### Logistic Regression
#### Performance
We only got a score of 62% accuracy in picking the 2nd difference of the confirmed cases, however, it is important to note that based on the confusion matrix, the model might still be useful.
#### <center>The Florida Next Day Model</center>
![Florida Model's Confusion Matrix alt ><](assets/fl_conf.png)
It is possible that the reason that a next day model, despite the virus having an incubation period of 2-12 days, might perform like this would be that many people might begin tweeting about feeling ill, and then going to get tested, and then they get their results the next day(s). While waiting for the results, they might begin tweeting more about the virus.
<br>
<br>
It is also important to note that the majority of the errors are false positives; the model predicted that the 2nd difference would be positive, when in fact, it was negative. Great! Couldn't be happier to be wrong! However of the 34 day forecasting window, only 3 false negatives, or cases when we predicted the 2nd difference would be negative, and it was positive. That's less than 9% predictions under rating the coming change in the 2nd difference.


