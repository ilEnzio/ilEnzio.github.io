---
layout: post
title: Bits Over Boyfriends
subtitle: Do Twitch Streamers Have to Sacrifice Quality of Life for Success?

cover-img: /assets/img/heartmoney.png
share-img: /assets/img/heartmoney.png

tags: [datascience, twitch, streaming, small_business, games, videogames]
---

### Don't Hate the Player...?

I have a gaming problem.  Well, my girlfriend has a gaming problem... Or does she...?  It breaks down like this:  My girlfriend is a part-time professional streamer - and  life isn’t all fun and games when your partner is a for profit gamer.  It's about making ends meet through viewer subscriptions, tips, and donations - with significant ad revenue only afforded to the elite.  She does way better than average as affliates go, but to really get ahead, my partner is seeking **partnership** status... from Twitch. That's where the really money is.   


![Bar Chart Monthly Affiliate Wage Comparison](https://ilenzio.github.io/assets/img/bar_chart_twitch_affiliate_average_monthly_wage_comparison.png)

Since most streaming takes place in the evening, what that means for me is a conspicuous lack of quality time.  Thus the competing interests arise:  I want more netflix and chill with my funny little honey,  while she is compelled to grind  - determined to grow her stream and revenue.  Conventional wisdom assumes having a successful stream takes dedication, passion, and lots of time. But is it worth the grind? Can data analysis and machine learning help us resolve the classic issue: How can we maximise Business Time without sacrificing _*Bidness time*_? 


### Build Me Up Buttercup

I attacked the problem by sourcing data from 3 sites - her entire 3 year streaming career analytics directly from [Twitch.com](https://www.twitch.tv/), channel specific revenue data from [Stream Labs](https://streamlabs.com/), and selected game data from [Sullygnome.com](https://sullygnome.com/).   
To understand the scope of the problem I immediately engineered two features.  **Streak** and **Activity**.  Streak represented how many consecutive days she streamed in order to build her audience.  

![Streamer Streak Line Chart](https://ilenzio.github.io/assets/img/streak_line_chart.png)

As you can see, after a year I managed to convince her to start scheduling days off.  Unfortunately I suspected that this might render the Streak feature less useful to a machine learning algorithm, so I engineered a feature called Activity, which represented the percentage of days, in the last 30 days, that she had streamed.  This would indicated if she had kept a consistent schedule within a 30 day period,without penalizing her for non-consecutive stream days. My hope was that the algorithm could determine any correlation between the consistency and revenue.  

![Streamer Activity Line Chart](https://ilenzio.github.io/assets/img/activity_line_chart.png)

After engineering a few more features including - **Total_Earnings**(all combined revenue), and **Player Mode**(whether the games streamed were single player, multiplayer or both) - I decided to look at some basic linear correlations.



![Absolute Value Correlation Matrix](https://ilenzio.github.io/assets/img/corr_Matrix_absolute_value_chart.png)


I had cause for hope when the plot revealed that **Chatters, Chat Messages, and Unique Viewers** took the **top 3** spots. In contrast, **Minutes Streamed was number 7!**  It was time to calculate some baseline metrics and build some models!

### Stuck in the Middle with...Metrics

Initially I determined that the raw data and target vector indicated a regression task, after all I was trying to predict revenue - a continuous variable - for a stream session.  However, after consideration I decided that framing the solution as classification would be more palatable, and increase relevance for stake holders.  In other words, rather than return a number figure it might be better to return a result that could scale with the relative success of the streamer, indicating whether given conditions would result in an upper percentile revenue session = “worth the grind”, or a lower percentile revenue session = “not worth the grind.”  At any rate there was certainly nothing stopping me from training one of each type of model.  My Baseline metrics were as follows: 


![Baseline Metrics Table](https://ilenzio.github.io/assets/img/baseline_metrics_table.png)


I decided on a **Ridge Regression** model and **Decision Tree Classifier**. I forked my Feature Matrix, and used the appropriate version of the Target Vector to train and fit each model.  After a little tuning our model produced some results...

![Streamer DecisionTreeClassifier Confusion Matrix](https://ilenzio.github.io/assets/img/twitch_tree_classifier_confusion_matrix_chart.png)

### What Machine Learning has Brought Together...
Both models beat our baseline, but what I really needed to get to the bottom of our Business Question was a look at the model’s permutation importances.   Was the ultimate path to Streamer success just about grinding for endless hours? Could my girlfriend justify increasing her Minutes Streamed over all else... or Nah?

![DecisionTreeClassifier Top10 Permutation Importance](https://ilenzio.github.io/assets/img/twitch_tree_classifier_permutation_importance_top15_bar_chart.png)

Minutes Streamed did not even make the Top 15 in permutation importance!! (While four of my engineered features did!) Besides the model's performance, the most exciting part of the analysis were the insights gained by taking a look at the shapley plots.  This gives a glimpse into how the model might use each feature in determining a particular prediction. Here is an example for one day:


![shapley plot example of def worth](https://ilenzio.github.io/assets/img/twitch_tree_classifier_shapley_top15_chart.png)

So according to our models, if you're seeking to maximise revenue, it's good to put in hours, but it's much more important to design your stream with chat engagement and participation in mind.  By the way…So far our best model does ~17% better than the baseline at predicting whether or not a given date will be worth streaming and i really, really, really hope to improve it. 

![model results table](https://ilenzio.github.io/assets/img/model_results_table.png)

##### Links:

[Colab Notebook link](https://github.com/ilEnzio/StarKells_Twitch_data/blob/master/ERLE_GRANGERII_DS18_UNIT02_Build_Bit_Over_Boyfriends_Final.ipynb)

[Project GitHub](https://github.com/ilEnzio/StarKells_Twitch_data)

[Portfolio](https://ilenzio.github.io/)

[CreatorHype](https://creatorhype.com/truth-about-twitch-affiliate/)

[SullyGnome's Twitch Statistics](https://sullygnome.com/)
