# Politics On Reddit: A Journey into the Dark Side of the American Political Landscape
By: Aryeh Gelfand(https://git.generalassemb.ly/aryehgelfand)

#### The Problem:

AmericanPolitics Debate.com is having a massive problem. A hacker broke into their system and mixed up the files for the Liberal and Conservative Political Discussion groups. I have been tasked with creating a model that can input text from the mixed up group and output an accurate prediction about which group it came from.

 
 ####  Executive Summary

I used data scraped from reddit.com. Specifically the subreddits, r/Conservative and r/The Liberal. In cleaning and modeling the data, I gained valuable insight into the patterns of liberal and conservative discussion groups and those who particpate in them. I was able to answer questions like: who uses more profanity? which group has livelier discssions? who has longer posts? what topics do each discuss? The more I dug into this data, the more it became clear that the groups had more similiarites than differences. Delving into the similarities and differences is what made this an interesting project for me.

### Conclusions and Recommendations

The moderation of the page had a very large effect on creating a uniqueness that the model could pick up on. Without the major unique terms, like profanity, the model bareful peformed above baseline. Soemthing like a political discussion group is very difficult to classify as both classes use th same terminology. It is not a good candidate for this type of classification. More robust cleaning could also help us achieve a better score, it could be that link words and other non important factirs contributed to the low accuracy score. However, it is clear that the datasets suffer from a lack of variance in word usage, and are therefore hard to distinguish from one another. This is probably why the TFIDF Vectorizer performed notably better than the Count Vectorizer. It was able to take the context of the document as a factor. In a situation like this where the subject matter is so similiar, context is everything. I would suggest focusing in on data that is hyper centered around one issue that we know is pertaining only to one group as opposed to both. If the text is dissimiliar it would be much easier to classify.
 
 
 
# Politics On Reddit: A Journey into the Dark Side of the American Political Landscape
By: Aryeh Gelfand(https://git.generalassemb.ly/aryehgelfand)

#### The Problem:

AmericanPolitics Debate.com is having a massive problem. A hacker broke into their system and mixed up the files for the Liberal and Conservative Political Discussion groups. I have been tasked with creating a model that can input text from the mixed up group and output an accurate prediction about which group it came from.

 
 ####  Executive Summary

I used data scraped from reddit.com. Specifically the subreddits, r/Conservative and r/The Liberal. In cleaning and modeling the data, I gained valuable insight into the patterns of liberal and conservative discussion groups and those who particpate in them. I was able to answer questions like: who uses more profanity? which group has livelier discssions? who has longer posts? what topics do each discuss? The more I dug into this data, the more it became clear that the groups had more similiarites than differences. Delving into the similarities and differences is what made this an interesting project for me.

### Conclusions and Recommendations

 - When making models for the future, focus on subjective metrics like Overall Qual, Ext Quality, and Overal Cond, these have more of an effect than objective metrics like number of bedrooms or baths.
 - Also, the strategy of creating a lot of interaction columns and dummy variables and then using regularizatioin to scale it back has been succesfull and should be replicated.
 - The missing data strategy was also successful but has to be done in conjunction with the data dictionary.
 - Eliminate outliers in the target variable as these can cause the distribution to become skewed. This will result in in accurate predictions
 
 
 
 ### Data Dictionary
title,selftext,subreddit,created_utc,author,num_comments,score,is_self,timestamp
 |Name of Field|Where Table exists|Description|Source|Datatype|
|---|---|---|---|---|
|"title""|liberal_df/conservative_df|Title of the reddit Post| https://api.pushshift.io/reddit/search/submission?subreddit=Liberal |object|
|"selftext"|liberal_df/conservative_df|The text within the post|https://api.pushshift.io/reddit/search/submission?subreddit=Liberal/https://api.pushshift.io/reddit/search/submission?subreddit=conservative|object|
|"subreddit"|liberal_df/conservative_df|Which subreddit the text came|https://api.pushshift.io/reddit/search/submission?subreddit=Liberal/https://api.pushshift.io/reddit/search/submission?subreddit=conservative|object|
|created_utc|liberal_df/conservative_df/'final_csv|'Unique code for each reddit post|https://api.pushshift.io/reddit/search/submission?subreddit=Liberal/https://api.pushshift.io/reddit/search/submission?subreddit=conservative|int64|
|num_comments"|liberal_df/conservative_df/'final_csv|The number of comments on the post|https://api.pushshift.io/reddit/search/submission?subreddit=Liberal/https://api.pushshift.io/reddit/search/submission?subreddit=conservative|int64|
|Score|act_2017/'final_csv|A submission's score is simply the number of upvotes minus the number of downvotes. |https://api.pushshift.io/reddit/search/submission?subreddit=Liberal/https://api.pushshift.io/reddit/search/submission?subreddit=conservative|int64|
|is_self|act_2017/'final_csv|Is the posttext only or does have links|https://api.pushshift.io/reddit/search/submission?subreddit=Liberal/https://api.pushshift.io/reddit/search/submission?subreddit=conservative|object|
|time_stamp|sat_2017/'final_csv|When was it posted on reddit|https://api.pushshift.io/reddit/search/submission?subreddit=Liberal/https://api.pushshift.io/reddit/search/submission?subreddit=conservative|dtime|

### References
 - https://www.reddit.com/r/Liberal/
 - https://www.reddit.com/r/Conservative/




 

