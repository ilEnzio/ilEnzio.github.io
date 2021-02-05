---
layout: post
title: Family Promise Labs
subtitle: Visualization Dashboard

cover-img: 
share-img: 

tags: [datascience, family_promise, spokane, homeless, shelter, dashboard]
---

### Project Background

Family Promise of Spokane is a homeless shelter that’s primary mission is to serve families in the local community.  The roadmap for the project included converting a 30 page, paper and pencil intake form to a digital process, improving an existing machine learning predictive exit outcome model, and creating two sets of visualizations - charts that would help non-technical caseworkers assess current and historical guest enrollment, and charts for model interpretation. 

As the member of the DS team tasked with creating descriptive statistics for the caseworkers the biggest concern I had was acquiring enough domain expertise to understand what stats to surface for the caseworkers, and how they might want to filter the results to create more meaningful, yet easy to understand visualizations.  

![FP Site Snippet](https://github.com/ilEnzio/ilEnzio.github.io/blob/master/assets/img/FamilyPSiteSnippet.png)

One of the technical challenges that we had to overcome involved the dashboard framework we choose to use in order to display visualizations - Streamlit.  The original design of Streamlit assumes a very simple single page style interface, however we needed to marry two distinct use cases into one tool with as little clutter as possible.  

Indeed we started with two separate “tools.”  The tool I built and was responsible for was a Descriptive Analytics Visualization dashboard.   The initial visualization I prototyped began as a univariate view of the distribution of  the guest enrollment population by current age.  I included an interactive legend which allowed the user to filter by gender - making the graph essentially bivariate.  I also included the ability to further filter the enrollment population by date range. 
	
The initial demo of the tool was well received by the stakeholder who gave immediate feedback.  He requested that the user be able to compare portions of the population defined by their exit outcome, such as: permanent exit, non-permanent exit, unknown exit.  Further the stakeholder wanted to be able to compare those “facets” of the enrollment population by relevant variables such as “Bed Nights Enrolled”.  
Thanks to the choice of framework, I was able to iterate and deliver a prototype of the functionality requested.  However the more intricate the visualizations became the more I felt the user may need to have an additional summary in order to be able to parse the information.  So I decided to create a summary table that indicated central tendencies for the comparison variables of each population facet.  For instance for a given date range the summary would provide the user with mean values of the relevant features according to a machine learning predictive model.  The user could choose which variable to graph and compare across each population facet.
	
![Main Dashboard Viz](https://github.com/ilEnzio/ilEnzio.github.io/blob/master/assets/img/FPMainViz.png)

The Data Science implementation of the product currently consists of an internal client tool with two main components: a Descriptive Statistics dashboard, and a Machine Learning Model Prediction dashboard.  

The Descriptive Statistics features an interactive chart displaying enrollment distribution.  The main chart can be filtered by date range via sliders.  The user can also choose to view the entire population distribution, Heads of Households, or Dependents. 
The dashboard also includes 3 side by side charts that display populations faceted by exit outcomes.  The user can choose which feature variable to graph and compare along all 3 charts. 

In order to help the user parse the comparison graphs there is also a summary table. The table attempts to reduce the complexity of comparing the populations by providing the central tendencies of each population. 

The Machine Learning dashboard allows the user to which model the to use in making an outcome prediction.  Then Displays charts of a choice of model interpretations: ELI5, PDP, SHAP.  Because this problem is considered one of classification, the dashboard also provides a confusion matrix visualizing the model’s predictive accuracy.  

Finally the user has the ability to choose a particular guest by selecting their case id, and receive a prediction as to possible guest outcome.  The results are visualized via a SHAP plot.
	
Demo Vid: ![Demo Vid](https://youtu.be/-fKb8AX-6j)


For the future of the product there is a lot of room to explore and surface statistics for the case worker and plenty of room to improve the interactivity and summary information.  As the future dev teams attain more domain knowledge, the visualizations and summaries can be tailored further.  Some aesthetic changes I would like to see involve highlighting mins and maxes of central tendencies for the user.  I would also like to see an animated change in the chart when the user decides to change the date range - thereby giving the case workers a visceral and motivating sense of the work that they are doing by helping guide families back to permanent housing.  

The main technical challenges will be migrating the internal tool implementation over to the existing client facing web app architecture.  
This project was significant in helping to further my career goals in many ways.  Firstly it was a  fantastic opportunity to work collaboratively on a data science team.  My role was distinct, but closely coordinated with the rest of the team.  Second, I was able to focus on something that was a bit of a weak point in my skill set - visualization.  By building a dashboard I gained much more confidence and can now leverage additional data engineering skills in future projects.  

