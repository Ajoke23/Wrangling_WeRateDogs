# Project 2: WeRateDogs Data Wrangling
## by Ajoke Yusuf
### Table of content
- Introduction
- Project Details
- Question(s) for Analysis
- Word Cloud Generation
- Conclusion
## Introduction
The project is aimed at Data wrangling, documenting wrangling process in a Jupyter Notebook, 
and showcasing them through analyses and visualizations using Python libraries. 
The dataset that is wrangled is the tweet archive [@DogRates](https://twitter.com/dog_rates), also known as [@WeRateDogs](https://en.wikipedia.org/wiki/WeRateDogs). 
‘WeRateDogs’ is a Twitter account that rates people's dogs with a humorous comment about the dog.
This rating is almost always have a denominator of 10.

## Project Details
The process carried out include:
1. Gathering Data
2. Assessing Data
3. Cleaning Data

#### Gathering Data
I gathered three different datasets that were obtained as following:
1. **Twitter archive file**: This data was provided in the project and was downloaded. I imported all 
the necessary python libraries needed and I used the pandas read_csv() function to read the file 
into a dataframe named twitter_archive.
2. **Tweet image prediction file**: The tweet image predictions was downloaded programmatically 
using the Requests library and the following 
(URL: https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv)
3. **Tweets_json_txt**: I used the tweet IDs in the ‘WeRateDogs’ Twitter archive, I queried the 
Twitter API for each tweet's JSON data using Python's Tweepy library and store each tweet's 
entire set of JSON data in a file called tweet_json.txt file. I also gathered each tweet's retweet
count and favorite count.
Each of the tweet's JSON data should was written in each line, then I read the .txt file into 
pandas DataFrame having the following columns: tweet ID, retweet count, and favorite count

#### Assessing Data
After gathering all the 3 datasets, I assess them visually and programmatically to detect quality 
and tidiness issues.
1. Visual Assessment: I printed the three different data frames individually in a jupyter notebook 
and scrolled through each of the dataset carefully. I also assessed the data after importing the file 
in Excel spreadsheet.
2. Programmatic Assessment: I used various python functions such as .shape, .info(),
.describe(), .dtypes, .value_counts(), .isna(), .duplicated()

#### Cleaning Data
Cleaning Data
Before I performed the cleaning process, I made a copy of all the 3 original datasets. During 
cleaning, I used the define, code, test framework and clearly documented it.
The following are the cleaning process carried out:
1. Dropped in_reply_to_status_id, in_reply_to_user_id, retweeted_status_id,
retweeted_status_user_id, expanded_urls, retweeted_status_timestamp columns.
2. Replaced None value in name column as np.nan and drop
3. Changed tweet_id datatype in archive table to object.
4. Changed timestamp datatype to datetime.
5. Removed jpg_url columns.
6. Dropped p1_dog, p2_dog, p3_dog.
7. Convert tweet_id data types to object.
8. Merge the 3 tables together based on 'tweet_id'.
9. Melt the p1, p2, p3 columns into a single column

## Question(s) for analysis
1. What's the average retweet count of each dog stage?
2. Which dog breed has the highest favorite count?
3. Which dog name(s) are popular?
4. Which dog stage is the most popular?
5. How many image(s) occured most in each tweet?
6. What are the top 5 dog breeds?
7. What are the top 5 breeds that has high rating value?
8. Is there any correlation between favourite count and retweet count?

## wordcloud Generation
In order to get the visual representation of dog breed text data, I decided to use WordCloud library. You can generate a visual representation based on the frequency of words and superimpose these word to any image or shape of your choice. In this project, I used the default background shape which is in "**rectangular format**".The more often certain words are mentioned in the data, the bigger those words will appear in this visualization.
In the image below, we could see that the biggest and boldest word is **Golden_retriever** which implies it's the most popular dog breed been rated by [@DogRates](https://twitter.com/dog_rates)

![wordcloud](https://user-images.githubusercontent.com/71567200/192900882-c58c3da8-75fe-4d6c-896a-277abcb90cb1.png)

## Conclusion
There exist a strong positive relationship between favorite count and retweet count.The goal of data wrangling is to assure quality of data  which has been achieved in
this project.
