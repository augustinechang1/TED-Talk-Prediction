# What factors determine the most viral TED Talks?

![header](images/AeroLeads-TED_banner-1.png)

## Goal
Answer the question above via multi linear regression analysis. Which ideas are truly worth sharing?:bulb:

## Data
- We used a dataset of 2550 unique entries from Kaggle, which contain information about talks. Features include types of ratings, Ted Talks (TEDx, TEDGlobal, etc), duration and published date of the video.

- The most painstaking process was cleaning & preprocessing of data. Using numpy and pandas, we created columns of individual features according to its categorical & continuous state and converted it to a dataframe. First OLS regression did not return statistically significant results, so we scaled the data to create a more accurate relationship between target and features, resulting in __70% R-squared__ and __p-values under 1%__. So, feel free to observe our data without your colored glasses.

- Throughout the process we were able to perform explanatory analysis, create dope graphs and answer some critical questions. Here are some:

## What type of videos will get most views?

![header](images/1.png)

- Boxplot of top ratings (x) against views (y). Jaw-dropping, funny, and fascinating videos tend to have in general more views than others. Correlation between views and top rated category for each video.

## How do rating attributes correlate with one another?

![header](images/4.png)

- Heatmap of the correlation of all rating types. The more red a box is means that the two features are highly correlated, for example "Unconvincing" and "Longwinded". This data helped with visualization for feature selection.

## How do people describe TED Talks by the event type?

![header](images/8.png)

- X-axis = Count of Talks
- People overwhelmingly attribute adjectives 'Inspiring' and 'Informative' to TED Talks.

## How do views correlate with date published and duration?

![header](images/5.png)

Negative correlation between months_ago and views (middle left graph). Older views have more views. Duration has no significant influence on number of views (left bottom graph).

## Train-Test-Split Results

![header](images/3.png)

- Regression result of trained data.
  - __Model Score__: 0.8428470625640061
  - __Mean Absolute Error__: 0.17139969599380347
  - __Mean Squared Error__: 0.056419962988649985
  - __Target Mean__: 7.999365338912133


- Features sorted by order of absolute value of coefficient:
(0.04, ‘TED’),
(0.03, ‘Unconvincing’),
(0.03, ‘TEDGlobal’),
(0.03, ‘Persuasive’),
(0.03, ‘Other_TED’),
(0.03, ‘Jaw_dropping’),
(0.03, ‘Fascinating’),
(0.02, ‘TEDSalon’),
(0.02, ‘TEDMED’),
(0.02, ‘Inspiring’),
(0.02, ‘Funny’),
(0.01, ‘minus_months’),
(0.01, ‘TEDx’),
(0.01, ‘TEDWomen’),
(0.01, ‘OK’),
(0.01, ‘Longwinded’),
(0.01, ‘Ingenious’),
(0.01, ‘Informative’),
(0.01, ‘Courageous’),
(0.01, ‘Beautiful’),
(0.0, ‘total’),
(0.0, ‘minutes’),
(0.0, ‘duration’),
(0.0, ‘Obnoxious’),
(0.0, ‘Confusing’)
