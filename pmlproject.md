---
title: "Practical Machine Learning Project: Predicting Exercise Classes"
author: "Logan Yang"
date: "August 23, 2014"
output: html_document
---
        
        


## Synopsis

Using devices such as *Jawbone Up*, *Nike FuelBand*, and *Fitbit* it is now possible to collect a large amount of data about personal activity relatively inexpensively. These type of devices are part of the quantified self movement – a group of enthusiasts who take measurements about themselves regularly to improve their health, to find patterns in their behavior. People rarely quantify how well they do the exercise. In this project, the goal will be to use data from accelerometers on the belt, forearm, arm, and dumbell of 6 participants. They were asked to perform barbell lifts correctly and incorrectly in 5 different ways. The machine learning model will predict the manner in which the participants did the exercise. This is the "classe" variable in the training set. 

# You may use any of the other variables to predict with. You should create a report describing how you built your model, how you used cross validation, what you think the expected out of sample error is, and why you made the choices you did. You will also use your prediction model to predict 20 different test cases.

### Data Processing

Load the data from the csv files, 


```r
training <- read.csv("pml-training.csv")
```

Subset the relevant variables and the complete cases. In this case, there are no missing values after subsetting the variables.




#### What are the top killer disasters in the US?

To answer the question of the harm on population health, we need to look at the two variables **FATALITIES** and **INJURIES**. Since the definition of *harm* is open to interpretation, here the method of weighting is used, giving a weight of 10 for the fatalities and 1 for the injuries, and creating a new variable called **HEALTH_HAZARD**. Here we summarize this new variable with a histogram and the summary command in r.



From the top 10 health hazard values, it is shown that the number one killer is heat (as for a single event, the total damage is discussed later), and then follows tornado. Ice storm is less frequently seen but can cause massive casualties as well. From the top 100 hazard values, the distinct events are heat, tornado, hurricane, flood, tsunami, and blizzard. The bar plot shows the highest frequency event among them is tornado.



We have summarized the top killer disasters with a single strike. Now we turn to the total health hazard caused by different kinds of events.



From this table we see clearly that tornadoes are the most harmful in terms of population health in the US.



#### Across the United States, which types of events have the greatest economic consequences?

Using a similar approach, we can look at the total property damage caused by different types of events.



From this graph, again we see tornadoes as the main hazard in terms of economic damages across the US.

### Results

To summarize the results, the number one killer is heat as for a single event. In terms of the total damage, whether it is population health or economic damages, tornado is the undisputed number one disaster across the US.


