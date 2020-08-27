---
layout: post
title: Business Time or Bidness Time?
subtitle: Do Twitch Streamers have to Sacrifice Quality of Life for Success?



tags: [datascience, twitch, streaming, small_business, games, videogames]
---

### Don't hate the player...?

I have a gaming problem.  Not really.  But my girlfriend has a gaming problem , which makes it my problem.  It goes something like this:  My girlfriend is a Twitch affiliate - a part-time professional streamer, and to be sure life isn’t all fun and games when your partner is a for profit gamer.  For Twitch streamers, making ends meet takes the form of viewer subscriptions, tips, and donations - with significant ad revenue only afforded to the elite.   

**Low performer Affilates vs Average Streamer vs Top Affilates/  Revenue/Followers vs StarKells**
![Bar Chart Monthly Affiliate Wage Comparison](https://ilenzio.github.io/assets/img/bar_chart_twitch_affiliate_average_monthly_wage_comparison.png)

Since most streaming takes place in the evening, what that means for me is a conspicuous lack of quality time.  Thus the competing interests arise:  I want more quality time with my funny little honey,  while she is compelled to grind  - growing her stream and revenue is understandably high priority.  Conventional wisdom assumes having a successful stream takes dedication, passion, and lots of time. But is it worth the grind? Can data analysis and machine learning help us resolve the classic issue: How can we maximise Business Time without sacrificing Bidness time? 


### Build Me Up Buttercup

I attacked the problem by sourcing data from 3 sites - her entire 3 year streaming career analytics directly from [Twitch.com](https://www.twitch.tv/), channel specific revenue data from [Stream Labs](https://streamlabs.com/), and selected game data from [Sullygnome.com](https://sullygnome.com/).   
To understand the scope of the problem and see what I was up against I immediately engineered two features.  Streak and Activity.  Streak represented how many consecutive days she streamed in order to build her audience.  

**streak line plot**

As you can see after a year I managed to convince her to start scheduling days off.  Unfortunately I suspected that this might render the **Streak** feature less useful to a machine learning algorithm so I engineered a feature called **Activity**, which represented the percentage of days, in the last 30 days, that she had streamed.  This would indicated if she had kept a consistent schedule with a 30 day period and without penalizing her for non-consecutive days. My hope was that the algorithm could determine any correlation between the consistency and revenue.  

**activity line plot**

After engineering a few more features including - **Total_Earnings** - all combined revenue, **Player Mode** - whether the games streamed were single player, multiplayer or both - I decided to look at some basic linear correlations


**possible Total_Earning vs player_mode scatter plot**

**correlation bar plot**

I had cause for hope when the plot revealed that Chatters, Chat Messages, and Unique Viewers took the top spots. While **Minutes Streamed was number 7!**  It was time to calculate some baseline metrics build some models!

### Stuck in the Middle with...Metrics

Initially I determined that the raw data indicated a regression problem, after all I was trying to predict revenue for a stream session.  However after consideration I decided that presenting the solution as classification would be more palatable, and increase relevance for stake holders.  In other words, rather than return a number figure it might be better to return a result that could scale with the relative success of the streamer, indicating whether given conditions would result in an upper percentile revenue session = “worth the grind”, or a lower percentile revenue session = “not worth the grind.”  
My Baseline metrics were as follows: 

**Regression Baseline Metrics:
MAE : we would be off by $24.54002158371927 on average.

**Classification Baseline Metrics:
Majority Classifier/Accuracy

I selected a LinearRegression model and DecisionTreeClassifier. I forked my X_Matrix, used the appropriate version of the y_target to train and fit each model.

**Validation results**
**Confusion Matrix** 

### What Machine Learning has brought Together, Let no Stream Tear Asunder!
After a little tuning our model  produced some results, that beat our baseline, but what I really needed to get to the bottom of our Business Question was a look at the model’s permutation importances.  Was the ultimate path to Streamer success just about grinding for endless hours?  

**permutation importance bar chart**

Besides the models performance  the most exciting part of the analysis was the insights gained by taking a look at the shapley plots.  This gives a glimpse into how the model might use used each feature in determining a particular prediction. 

**shapley plots**

By the way…So far our best model does ~18% better than the baseline at predicting whether or not a given date will be worth streaming and i really, really, really hope to improve it. 


##### Links:

[Colab Notebook link]

[Project GitHub]

[Portfolio](https://ilenzio.github.io/)

[Diamonds & Desire Boudoir Photography](https://www.diamondsanddesire.com/)

[ZipRecruiter Photographer Salary Reference](https://www.ziprecruiter.com/Salaries/How-Much-Does-a-Professional-Photographer-Make-an-Hour)
