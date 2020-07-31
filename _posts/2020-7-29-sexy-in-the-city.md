---
layout: post
title: Sexy in the City
subtitle: Can data driven analysis help you stop worrying and increase your hourly wage by $35 while photographing people in undies?

cover-img: /assets/img/DSC_6392-Edit-Edit.jpg
share-img: /assets/img/DSC_6392-Edit-Edit.jpg

tags: [datascience, photography, boudoir, small_business, jacksonville, florida]
---

  With the rise of social media and cell-phones it’s safe to say anyone can consider themselves to be an accomplished amateur photographer.  But while the hobbyist can point and shoot indiscriminately, in order to earn a living creating images, the professional must be discerning about what they capture - and thus the various genres of professional photography arise.  Parsing the topic even further, if your metric is gross income, all photographic genres are not created equal.  
  
  Which brings us to the subject of our exploration - a relatively obscure but potentially lucrative niche genre of photography, called Intimate Portraiture, or more commonly known as Boudoir Photography.   If photography studios were restaurant’s, think of the boudoir photo studio as the equivalent of a restaurant that only serves lunch or breakfast…in bed. 

  For this project I was able to source data from the most successful boudoir photography studio in Northeast Florida - a little mom-and-pop shop called [Diamonds and Desire Boudoir Photography](https://www.diamondsanddesire.com/). To put the success of this two person operation in context, the nation wide average hourly wage for professional photography according to ZipRecruiter as of July 20, 2020 was **$21/hour**, while the average for northeast florida was **$19/hour**.  However D&D Photography averages **_$82/man-hour_**.  
  

![Chart comparing photog average hourly wage](https://ilenzio.github.io/assets/img/bar_chart_average_hourly_wage_comparison.png)


Although the business had been in operation for over 10 years, and the studio did have other sources of income(other genres of photography, studio equipment rentals, etc), the data set I was able to source amounted to gross sales totaling a little less than a quarter of a million dollars over a 6 year period. With that said, the goal of the project was to give 3 data driven, actionable insights, based on an anatomy of the specific business model of Diamonds and Desire. That business model anatomy consisted of: Preshoot Consultation(Booking the client), Photoshoot and Post Processing (executing the service), and Sales Sessions.

### Delectable Data left on the table
Let’s begin with insight relevant to the Preshoot consultation as this grants further context into the domain in general. The data for the project was compiled from records of the consultations and records of sales. So while it does include features like booking date, date of birth, zip code, session fee, and sales total, etc. There were other variables that were almost always revealed due to the nature of the consultation, but not recorded with the proper nuance or consistency: Occasion of shoot( anniversary, birthday, father’s day, valentine’s day, x-mas, or perhaps no occasion!). Being located in a navy town, many of the clients were in the military, or military spouses, but this was not consistently recorded. Ethnicity and gender, were also not recorded with enough nuance to be useful. From the sales information, the sales total and product quantity/type was documented, but the type of photograph was not categorized in the sales data with enough nuance. Were the photographs close up, wide shots, black and white, color, high key, or low key? These are all metrics which could affect the businesses marketing decision and perhaps shooting practices. And once again this is data that was collected and available, but just not suitably recorded. Therefore I would recommend adding these to the variables recorded going forward.
 

### "Hmm! I like my …” - anonymous client
As for insight regarding the second facet of the business, the actual photoshoot, there was one particular feature extremely relevant to service execution and the general success of the business. The “Favorite” variable was defined as which body part the client was most interested in highlighting or having exceptional photographs of. So it follows that the Favorite feature revealed what most clients expect a boudoir photographer to be good at shooting. Thus, while a family photographer would be expected to deliver solid group shots - relying on skill at herding and staging people, a succesful wedding photographer might develop skill at recognizing or staging beautiful moments, and a headshot specialist might gather an arsenal of corny jokes. But in boudoir photography, the data shows, that among clients that have a preference, the expectation by an almost two to one margin is for exceptional shots of… the booty.

![Chart of Favorite values counts](https://ilenzio.github.io/assets/img/bar_chart_top_ten_favorites.png)

To thrive one must cultivate an appreciation of the booty, in all sizes and shapes - the right wardrobe and posing for the booty, the right angle and lens for the booty. The bottom line… your corny jokes aren’t going to help, because if you’re going to meet client expectations, it’s literally your job to present the booty in it’s best light.

### Too Sexy for my Zip Code?
Now it’s time to get to, dare I say, the sexist feature in the data set: Sales Total. Ideally we’d be able to gather from the data which other feature correlates most closely with a high sales total. Although there’s a common tendency to be seduced by the notion of wealth and zip code tracking closely, our data did not support this. In this business domain, zip code does not correlate with a higher sales mean.

![Chart of Zip code vs Sales Total](https://ilenzio.github.io/assets/img/zip_code_vs_total_sales.png)

Even when we examine the age of the clients and sales records there is still no obvious correlation. All age ranges tend toward the same mean sales total.

![Box Plot of Age Range vs Sales Total](https://ilenzio.github.io/assets/img/boxplot_age_range_v_sales.png)

These were disappointing results as they could have been exploited via marketing. The quest for the elusive highly correlated feature-pair seemed lost, until we examined one innocuous variable: “Hair.” This feature was simply a record of whether the photographer was to schedule a professional hairstylist on the day of the shoot. (Professional make up artist services were included with every shoot.) The distribution of make-up only clients vs those who chose to pay an additional fee for professional hair styling is illustrated below:

![Pie chart Make-up only vs Hair and Make-up](https://ilenzio.github.io/assets/img/pie_chart_makeup_v_hair.png)

### Hair Love
Surprisingly, when compare to each other the average sales total for a client who opted for a hair stylist was nearly $100 more than clients who only received professional makeup. That is an 11% increase in sales at no expense to the business! So, clients who had already spent additional money for the service went on to spend even more.

![Chart of Make-up only vs Hair and Make-up mean sales](https://ilenzio.github.io/assets/img/bar_sales_mu_v_hair.png)

But the most starling consequence of this discovery was yet to come. It turns out that since professional hair service takes about 1 hour of the photoshoot time, that is time that the photographer is free to do other things, be it book clients and administrative tasks, or pursue leisure. In addition, the amount of photos taking during the shoot are a factor of the time spent shooting. Thus one hour less photos taken reduce the post processing workload and time. So, where as a shoot with make-up only, may take 9 hours (1 consult, 3 hour shoot, 4 hours post, 1 hour sales) and result in an average sale of $711 or \$79/hour. A shoot with make up and professional hair styling will only take 7 hours (1 consult, 2 hour shoot, 3 hours post, 1 hours sales) and result in an average sale of \$803 or \$114/hour! Therefore a everytime you can convince a client to add professional hair styling to the shoot you increase your expected value by \$35 an hour! *  (With the icing on the cake being increased morale for the team because the stylist more than doubles their income for the day.)



### Conclusion:
In summary, this project shows that even a “mom-and-pop shop” small business can gain valuable insights across all aspects their business domain through data analysis. By nature these insights are specific and revelvant to a particular business model and positively effect the bottom line.

\* A two sample TTest was conducted with the following results: Assuming a 95% confidence level - Based on a tstat of -1.58 and pvalue of approximately .11499, I FAIL to reject the null hypothesis that clients who get make-up only spend the same amount on average as clients who get professional hair and make-up.


##### Links:

[Temp Notebook link](https://colab.research.google.com/drive/1HvEZxyCJy3YvJYm4mUvO5qGwDHKAo2oR?usp=sharing)

[Project GitHub](https://github.com/ilEnzio/Sexy_In_The_City)

[Portfolio](https://ilenzio.github.io/)

[Diamonds & Desire Boudoir Photography](https://www.diamondsanddesire.com/)

[ZipRecruiter Photographer Salary Reference](https://www.ziprecruiter.com/Salaries/How-Much-Does-a-Professional-Photographer-Make-an-Hour)

