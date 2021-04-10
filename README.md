# TwitterEnvironmentalNetwork
Datasets for course project of [Social Data Science](https://github.com/dgarcia-eu/SocialDataScience) - ETH Zurich

Group members: Tianyuan Wang, Haonan Yang, Yuehan Yang, Yuanwen Yue

Supervisor: [Prof. David Garcia](http://dgarcia.eu/)

### Introduction

The datasets were collected using [rtweet](https://github.com/ropensci/rtweet) and Twitter's offical REST [API](https://developer.twitter.com/en/docs/twitter-api). The datasets contain the following five parts. Each dataset is provided in both csv and Rds formats. You can also use [all.RData]() to load all the data.

- Environmental celebrities's profiles [[users.csv](users.csv)] / [ [users.Rds](users.Rds)]
- Environmental related tweets [[environmental_tweets.csv](environmental_tweets.csv)] / [ [environmental_tweets.Rds](environmental_tweets.Rds)]
- Replies in all conversations [[repliesAll.csv](repliesAll.csv)] / [ [repliesAll.Rds](repliesAll.Rds)]
- Sample replies for validation [[sampled_replies.csv](sampled_replies.csv)] / [ [sampled_replies.Rds](sampled_replies.Rds)]
- Manual scores for sample replies [[manual_scores.csv](manual_scores.csv)] / [ [manual_scores.Rds](manual_scores.Rds)]


####  1 Environmental celebrities's profiles
- Source: [[users.csv](users.csv)] / [ [users.Rds](users.Rds)]
- Description: the twitter profiles of 240 selected environmental celebrities. We referred  to three public lists of top environmental influencers selected by [Climate Week NYC](https://www.climateweeknyc.org/climate-groups-top-100-twitter-accounts-2020), [Onalytica](https://onalytica.com/blog/posts/environmental-sustainability-top-100-influencers/) and [Corporate Knights](https://www.corporateknights.com/channels/connected-planet/top-100-eco-influencers-twitter-14295615/). The twitter list can be found [here](https://twitter.com/i/lists/1371127388474462208).
- Column: user_id, name, screen_name, location, description, url, followers_count	friends_count, listed_count, created_at, favourites_count, etc.

####  2 Environmental related tweets
- Source: [[environmental_tweets.csv](environmental_tweets.csv)] / [ [environmental_tweets.Rds](environmental_tweets.Rds)]
- Description: To filter tweets regarding environment and climate changes of the chosen celebrities, we browsed all the 240 celebrities’ recent 1000 tweets and pre-selected keywords. Then, we ran grep function in R to filter all queried tweets and obtained 45,298 related tweets.
- Column: 
  - screen_name:  screen name of user who posted  this Tweet
  - tweet_url: url of this Tweet

####  3 Replies in all conversations
- Source: [[sampled_replies.csv](sampled_replies.csv)] / [ [sampled_replies.Rds](sampled_replies.Rds)]
- Description: The replies in all conversations. There are 534135 records in total.
- Column:
  - conversation_id: conversation id of this reply.
  - user_id: id of user who posted  the original Tweet that started the conversation. 
  - screen_name: screen name of user who posted  the original Tweet that started the conversation. 
  - author_id: id of user who posted the reply
  - created_at: the time this reply was created
  - text: the content of this reply

####  4 Sample replies for validation
- Source: [[.csv]()] / [ [.Rds]()]
- Description: a random sample of 500 replies used for validation
- Column: 
  - x: the content of this reply
  
####  5 Manual scores for sample replies
- Source: [[manual_scores.csv](manual_scores.csv)] / [ [manual_scores.Rds](manual_scores.Rds)]
- Description: the sentiment score of the sample of 500 replies labelled by group memers.
- Column: 
  - score1: scoring of group member 1
  - score2: scoring of group member 2
  - score3: scoring of group member 3
  - score4: scoring of group member 4
  - mean: average of the 4 group members’ scores, used as the true value

###  Use terms and notice

The use of the data should comply with Twitter's [developer agreement and policy](https://developer.twitter.com/en/developer-terms/agreement-and-policy). If you have any questions with the data, please contact us by [yuayue@ethz.ch](mailto: yuayue@ethz.ch).
