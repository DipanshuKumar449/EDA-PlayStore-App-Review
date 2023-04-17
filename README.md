# EDA-PlayStore-App-Review

### Abstract:
-------------------------------------
* Google play store is the official app store for all devices operating on the Android OS. It allows the users to browse and download the apps that are developed with the android software development kit (SDK).
* Apart from offering android applications and games, it also serves as a digital media store offering music, books, movies, and television programs.
* User ratings and reviews can significantly increase the number of app downloads; hence it is important to analyse the parameters which lead to users giving positive feedback and higher rating.
* Though this exploratory data analysis, we can understand and discover the key factors responsible for app engagement and success.
--

### Introduction:
--------------------------------------
We are provided with two datasets:

* Play_store_data: It contains the basic details of the app like number of user reviews, ratings, etc.
* User_reviews: It contains the user reviews and its sentiment score for the respective app. We need to explore and analyze the data to discover key factors responsible for app engagement and success.
The contents of play_store_data are:
* App: It contains the name of the app with a short description (optional).
* Category: This section gives the category to which an app belongs. In this dataset, the apps are divided among 33 categories.
* Size: The disk space required to install the respective app.
* Rating: The average rating given by the users for the respective app. It can be in between 1 and 5.
* Reviews: The number of users that have dropped a review for the respective app.
* Installs: The approximate number of times the respective app was installed.
* Type: It states whether an app is free to use or paid.
* Price: It gives the price payable to install the app. For free type apps, the price is zero.
* Content rating: It states which age group is suitable to consume the content of the respective app.
* Genres: It gives the genre(s) to which the respective app belongs.
* Last updated: It gives the day in which the latest update for the respective app was released.
* Current Ver: It gives the current version of the respective app.
* Android Ver: It gives the android version of the respective app.
The contents of user_reviews are:
* App: It contains the name of the app with a short description (optional).
* Translated_Review: It contains the English translation of the review dropped by the user of the app.
* Sentiment: It gives the attitude/emotion of the writer. It can be ‘Positive’, ‘Negative’, or ‘Neutral’.
* Sentiment_Polarity: It gives the polarity of the review. Its range is [-1,1], where 1 means ‘Positive statement’ and -1 means a ‘Negative statement’.
* Sentiment_Subjectivity: This value gives how close a reviewer’s opinion is to the opinion of the general public. Its range is [0,1]. Higher the subjectivity, closer is the reviewer’s opinion to the opinion of the general public, and lower subjectivity indicates the review is more of a factual information.

After loading the dataset, we can start the exploration but before that, we need to check and see that the dataset is ready for performing several exploration operations or not, so let’s first have a look at the structure and the manner in which the data is organized.


### Data Pipeline:
-------------------------------------
* Data Cleaning

Our data set contains a large number of null values in the rating column, so we drop them. Some of the columns have a smaller number of null values, so we replace the null values in these columns with the mode value of that particular column. Our data set also contain the duplicate rows for a single application. We also drop the duplicate rows because the rows contain the identical data. Also drop the rows, which have rating greater than 5.

* Data Transforming

From the information of data frame, we can see that all the columns except rating have the object data type but some of the columns like, reviews, size, installs and price have the numerical value. So, we have to transform them in proper data type and also remove the unwanted values from the numerical columns like ‘+’ and ‘,’ from installs and ‘$’ from price. In the size column we have some values in KB and some values in MB, so we transform all the values in MB.

* Exploratory Data Analysis

After establishing a good sense of each feature, we proceeded with plotting a pairwise plot between all the quantitative variables to look for any evident patterns or relationships between the features. There is a high variance in the number of installs and in number of reviews. To overcome this problem, we add two new columns to the data frame named: log_installs and log_review, which contain the logarithmic values of installs and review columns, respectively.

* Single Variate Analysis

After that we analysis all the columns one by one to examine whether the particular column contain some useful information or not:

* Category

We breakdown the apps by category and observe that family and game categories have the maximum number of apps in the play store. Weather, house and home, comics, events, beauty, and parenting are the categories which have a few numbers of apps.

* Data wrangling

Apart from this, two new columns were added to the main data frame, namely, “Rating Group”, and “Revenue”. This is done to improve simplify the analysis and come up with different meaningful visualizations.

Rating Group: This column groups the apps based on the average user rating. (4-5: Top rated, 3-4: Above average, 2-3: Average, 1-2: Below average).

Revenue: This column gives the revenue generated by the app through app installs alone. By doing these operations on the original dataset, we are ready with the data pipeline, and data visualizations can be done on it. All the apps in play store have the rating between 0.5 to 5. Maximum apps have the rating between 3.8 to 4.5.


### Conclusion:
--------------------------------
These are some of the aspects that the developer should research before proceeding with the app development. By conducting a simple exploratory data analysis (EDA) on the play store dataset, we not only eliminate avoidable risks of failure, but we may also be able to provide better ideas for building the app.

From this EDA project, the following concepts were learnt:
1. Basic inspection of the raw data.
2. Handing the duplicate, error and NaN values present in the dataset, i.e., cleaning the data.
3. Using different Python functions and libraries to clean and manipulate data.
4. Data wrangling to come up with different insights on the data.
5. Designing multiple visualizations to summarize the information in the dataset and successfully communicate the results and trends to the reader.
