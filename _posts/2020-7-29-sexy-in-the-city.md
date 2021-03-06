---
layout: post
title: Sexy in the City
subtitle: Can data driven analysis help you stop worrying and increase your hourly wage by $35 while photographing people in undies?

cover-img: /assets/img/DSC_6392-Edit-Edit-2.jpg
share-img: /assets/img/DSC_6392-Edit-Edit-2.jpg

tags: [datascience, photography, boudoir, small_business, jacksonville, florida]
---

### A Saucy data source

For this project I was able to source data from the most successful boudoir photography studio in Northeast Florida - a little mom-and-pop shop called [Diamonds and Desire Boudoir Photography](https://www.diamondsanddesire.com/).  Put in context, the nation wide average hourly wage for professional photography according to ZipRecruiter as of July 20, 2020 was **$21/hour**, while the average for northeast florida was **$19/hour**. However D&D Photography averages **_$82/man-hour_**.

![Chart comparing photog average hourly wage](https://ilenzio.github.io/assets/img/bar_chart_average_hourly_wage_comparison.png)

For the secret to their success - a bit of set up:  A photography student once asked me what the distinction was between an amateur and a “pro”?  I countered: “You, of course mean ‘What’s the most important distinction?’ ” Skill Level?  No.  Certainly not the equipment or tools they use.  Indeed, the most important and useful distinction is a hobbyist can aim and shoot indiscriminately, but in order to earn a living creating images, the professional must be discerning about what they capture.  Where you point the camera is paramont - thus the various genres of professional photography arise.  And monetarily all photographic genres are not created equal. 

Our analysis concerns a relatively obscure but lucrative niche genre called Intimate Portraiture, or  Boudoir Photography. If photography studios were restaurant’s, think of the boudoir photo studio as the equivalent of a restaurant that only serves lunch or breakfast…in bed.

Since the data set  represented concrete sales data totaling a little less than a quarter of a million dollars, the project goal was equally concrete: Give three data centric, actionable insights, parallelling the specific business model of Diamonds and Desire. That business model consisted of: Pre-shoot Consultation(Booking the client), Photoshoot (executing the service), and Sales Sessions.

### Data left forlorn...  

The data for the project was compiled from records of the **Preshoot Consultation** and records of sales. So while it does include features like booking date, date of birth, zip code, session fee, and sales total, etc. There were other variables that were almost always revealed due to the nature of the consultation, but not recorded with the proper nuance or consistency: Occasion of shoot( anniversary, birthday, father’s day, valentine’s day, x-mas, or perhaps no occasion!). Being located in a navy town, many of the clients were in the military, or military spouses, but this was not consistently recorded. Ethnicity and gender were also not recorded with enough nuance to be useful.  

From the sales information, the sales total and product quantity/type was documented, but the type of photograph was not categorized in the sales data with enough nuance. Were the photographs close up, wide shots, black and white, color, high key, or low key? These are all metrics which could affect the business’s marketing decision and perhaps shooting practices. And once again this is data that was made available, but just not suitably recorded. Therefore I would recommend adding these to the variables recorded going forward.

 * **Type of Photograph Purchased** (Color vs BW, Close-up vs Wide, Hi vs Low Key)
* **Occassion of shoot** (None, Anniversary, V-day, X-mas, etc)  
* **Gender** (w/ suitable nuance)
* **Ethnicity** (w/ suitable nuance)

### "Hmm! I like my …” - anonymous client
Insight 2 - Regarding the actual photoshoot there was one feature extremely relevant to service execution and the general success of the business. The **“Favorite”** variable was defined as which body part the client was most interested in highlighting or having exceptional photographs of. So it follows that the Favorite feature revealed what most clients expect a boudoir photographer to be good at shooting. While a family photographer would be expected to deliver solid group shots - relying on skill at herding and staging people, a succesful wedding photographer might develop skill at recognizing or staging beautiful moments, and a headshot specialist might gather an arsenal of corny jokes.  But in boudoir photography, the data shows, that among clients that have a preference, the expectation by an almost two to one margin is for exceptional shots of… the booty.

![Chart of Favorite values counts](https://ilenzio.github.io/assets/img/bar_chart_top_ten_favorites.png)

To thrive one must cultivate an appreciation of the booty, in all sizes and shapes - the right wardrobe and posing for the booty, the right angle and lens for the booty. The bottom line… your corny jokes aren’t going to help, because if you’re going to meet client expectations, it’s literally your job to present the booty in it’s best light.

### Too Sexy for my Zip Code?
Now it’s time to get to, dare I say, the **sexist feature** in the data set: **Sales Total**. Ideally we’d be able to gather from the data which other feature correlates most closely with a high sales total. Although there’s a common tendency to be seduced by the notion of **wealth and zip code** tracking closely, our **data did not support** this. In this business domain, zip code does not correlate with a higher sales mean.

![Chart of Zip code vs Sales Total](https://ilenzio.github.io/assets/img/zip_code_vs_total_sales.png)

Even when we examine the age of the clients and sales records there is still **no obvious correlation**. All age ranges tend toward the same mean sales total.

![Box Plot of Age Range vs Sales Total](https://ilenzio.github.io/assets/img/boxplot_age_range_v_sales.png)

These were disappointing results as they could have been exploited via marketing. The quest for the elusive highly correlated feature-pair seemed lost, until we examined one innocuous variable: “Hair.”  

This feature was simply a record of whether the photographer was to schedule a professional hairstylist on the day of the shoot. (Professional make up services were included with every shoot.) The distribution of make-up only clients vs those who chose to pay an additional fee for professional hair styling is illustrated below:

![Pie chart Make-up only vs Hair and Make-up](https://ilenzio.github.io/assets/img/pie_chart_makeup_v_hair.png)

### Hair Love
Surprisingly, when compared to each other the average sales total for a client who opted for a hair stylist was **nearly $100 more** than clients who only received professional makeup. That is an **11% increase in sales** at no expense to the business! So, clients who had *already spent additional money* for the service went on to spend even more.

![Chart of Make-up only vs Hair and Make-up expectation value](https://ilenzio.github.io/assets/img/ev_sales_mu_v_hair.png)

But the most startling consequence of this discovery was yet to come. Ironically, the photographer works fewer hours to service a client that gets more services.  Hairstyling takes up approximately 1hr of the shoot and results in less photos to process, increasing the expected value of the shoot by $35/hour! \*


### Boudoir Bottom Line:
In summary, this project shows that even a “mom-and-pop” small business can gain valuable insights across all aspects their business domain through data analysis. By nature these insights are specific and revelvant to a particular business model and positively effect the bottom line.

\* A two sample **TTest** was conducted with the following results: Assuming a **95% confidence level** - Based on a **tstat of -1.58** and **pvalue of approximately .11499**, I **FAIL to reject the null hypothesis** that clients who get make-up only spend the same amount on average as clients who get professional hair and make-up.


##### Links:

[Colab Notebook link](https://colab.research.google.com/drive/1HvEZxyCJy3YvJYm4mUvO5qGwDHKAo2oR?usp=sharing)

[Project GitHub](https://github.com/ilEnzio/Sexy_In_The_City)

[Portfolio](https://ilenzio.github.io/)

[Diamonds & Desire Boudoir Photography](https://www.diamondsanddesire.com/)

[ZipRecruiter Photographer Salary Reference](https://www.ziprecruiter.com/Salaries/How-Much-Does-a-Professional-Photographer-Make-an-Hour)

