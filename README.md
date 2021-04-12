# TwitterEnvironmentalNetwork

This repository contains the R markdown files and datasets for course project of [Social Data Science](https://github.com/dgarcia-eu/SocialDataScience) - ETH Zurich

Group members: Tianyuan Wang, Haonan Yang, Yuehan Yang, Yuanwen Yue

Supervisor: [Prof. David Garcia](http://dgarcia.eu/)

### Introduction

The datasets were collected using [rtweet](https://github.com/ropensci/rtweet) and Twitter's offical REST [API](https://developer.twitter.com/en/docs/twitter-api). The datasets contain the following ten parts. Each dataset is provided in both csv and Rds formats (Due to Github storage limit, we only provide Rds format for repliesAll). You can also use [all.RData](data/all.RData) to load all the data.

- Environmental celebrities's profiles [[users.csv](data/users.csv)] / [ [users.Rds](data/users.Rds)]
- Environmental celebrities's fields label [[celebrity.csv](data/celebrity.csv)] / [ [celebrity.Rds](data/celebrity.Rds)]
- Environmental celebrities subset with fields label [[fieldsdf.csv](data/fieldsdf.csv)] / [ [fieldsdf.Rds](data/fieldsdf.Rds)]
- Environmental keywords [[keyword.csv](data/keyword.csv)] / [ [keyword.Rds](data/keyword.Rds)]
- Environmental related tweets [[environmental_tweets.csv](data/environmental_tweets.csv)] / [ [environmental_tweets.Rds](data/environmental_tweets.Rds)]
- Environmental related tweets with reply [[tweets_with_reply.csv](data/tweets_with_reply.csv)] / [ [tweets_with_reply.Rds](data/tweets_with_reply.Rds)]
- Replies in all conversations [[repliesAll.Rds](data/repliesAll.Rds)]
- VADER sentiments scores for all celebrities [[vader_result.csv](data/vader_result.csv)] / [ [vader_result.Rds](data/vader_result.Rds)]
- Sample replies for validation [[sampled_replies.csv](data/sampled_replies.csv)] / [ [sampled_replies.Rds](data/sampled_replies.Rds)]
- Manual scores for sample replies [[manual_scores.csv](data/manual_scores.csv)] / [ [manual_scores.Rds](data/manual_scores.Rds)]


### Data details
####  1 Environmental celebrities's profiles
- Source: [[users.csv](data/users.csv)] / [ [users.Rds](data/users.Rds)]
- Description: the twitter profiles of 240 selected environmental celebrities. We referred  to three public lists of top environmental influencers selected by [Climate Week NYC](https://www.climateweeknyc.org/climate-groups-top-100-twitter-accounts-2020), [Onalytica](https://onalytica.com/blog/posts/environmental-sustainability-top-100-influencers/) and [Corporate Knights](https://www.corporateknights.com/channels/connected-planet/top-100-eco-influencers-twitter-14295615/). The twitter list can be found [here](https://twitter.com/i/lists/1371127388474462208).
- Column: user_id, name, screen_name, location, description, url, followers_count	friends_count, listed_count, created_at, favourites_count, etc.

####  2 Environmental celebrities's fields label
- Source: [[celebrity.csv](data/celebrity.csv)] / [ [celebrity.Rds](data/celebrity.Rds)]
- Description: Based on Twitter profile and Wikipedia, celebrities were labeled into scientists, environmentalists, businessmen, politicians, athletes, writers/journalists, actors/singers/hosts, organisations, social activists and NGO officers.
- Column: user_id, name, screen_name, location, field.

####  3 Environmental celebrities subset with fields label
- Source: [[fields.csv](data/fields.csv)] / [ [fields.Rds](data/fields.Rds)]
- Description: We conduct network analysis on 240 celebrities and screened out 173 celebrities who have at least one connection with other celebrities
- Column: 
  - id: user id of this celebrity
  - name: screen name of thie celebrity
  - deg: node degree of this celebrity
  - community: community id which this celebrity belongs to
  - kcore: kcore of this celebrity
  - field: field of this celebrity

####  4 Environmental keywords
- Source: [[keyword.csv](data/keyword.csv)] / [ [keyword.Rds](data/keyword.Rds)]
- Description: We browsed all the 240 celebrities' recent tweets and selected 35 keywords.
- Column: 
  - keyword: keywords related to environmental protection
  - importance: relevance to environmental protection
  - notes: some notes
  - synonyms: synonyms of keywords

####  5 Environmental related tweets
- Source: [[environmental_tweets.csv](data/environmental_tweets.csv)] / [ [environmental_tweets.Rds](data/environmental_tweets.Rds)]
- Description: We manually checked all the 240 celebrities' recent tweets regarding environmental issues and selected 35 keywords. Then, we ran grep function in R to filter the last 1,000 tweets of each celebrity and obtained 45,298 related tweets.
- Column: 
  - screen_name:  screen name of user who posted this Tweet
  - tweet_url: url of this Tweet

####  6 Environmental related tweets with reply
- Source: [[tweets_with_reply.csv](data/tweets_with_reply.csv)] / [ [tweets_with_reply.Rds](data/tweets_with_reply.Rds)]
- Description: Before crawling replies, filter tweets based on two conditions:
  1. The reply_count should not be 0, which means that there must be at least one reply to this tweet.
  2. The tweet id should be the same with the conversation id, which means this tweet should be the original Tweet that started the conversation.
- Column: 
  - author_id: the id of the author who posted this tweet
  - id: tweet id
  - conversation_id: the id of the conversation to which this tweet belongs
  - public_metrics: includes retweet_count, reply_count, like_count, quote_count
  - created_at: the time this tweet was created
  - text: the text content of this tweet

####  7 Replies in all conversations
- Source: [[repliesAll.Rds](data/repliesAll.Rds)]
- Description: The replies in all conversations. There are 534135 records in total.
- Column:
  - conversation_id: conversation id of this reply.
  - user_id: id of user who posted  the original Tweet that started the conversation. 
  - screen_name: screen name of user who posted  the original Tweet that started the conversation. 
  - author_id: id of user who posted the reply
  - created_at: the time this reply was created
  - text: the content of this reply

####  8 VADER sentiments scores for all celebrities
- Source: [[vader_result.csv](data/vader_result.csv)] / [ [vader_result.Rds](data/vader_result.Rds)]
- Description: VADER sentiments scores for all celebrities.
- Column:
  - screen_names: screen name of the celebrity.
  - vader_mean: mean of vader scores of all the replies to the celebrity's selected tweets. 
  - vader_sd: standard deviation of vader scores of all the replies to the celebrity's selected tweets. 
  - comments_num: number of replies to the celebrity's selected tweets. 

####  9 Sample replies for validation
- Source: [[sampled_replies.csv](data/sampled_replies.csv)] / [ [sampled_replies.Rds](data/sampled_replies.Rds)]
- Description: a random sample of 500 replies used for validation
- Column: 
  - x: the content of this reply
  
####  10 Manual scores for sample replies
- Source: [[manual_scores.csv](data/manual_scores.csv)] / [ [manual_scores.Rds](data/manual_scores.Rds)]
- Description: the sentiment score of the sample of 500 replies labelled by group memers.
- Column: 
  - score1: scoring of group member 1
  - score2: scoring of group member 2
  - score3: scoring of group member 3
  - score4: scoring of group member 4
  - mean: average of the 4 group members’ scores, used as the true value

###  Use terms and notice

The use of the data should comply with Twitter's [developer agreement and policy](https://developer.twitter.com/en/developer-terms/agreement-and-policy). If you have any questions with the data, please contact us by yuayue@ethz.ch.
