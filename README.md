# Phase one project
project submission
![Movies_ _TV_films_2016 svg](https://github.com/ed-gar-k/final-PH-repo/assets/109956677/c2aec624-193a-4f63-9fc4-9593f3c9515a)

#### INTRODUCTION-overview
 This project is designed to address the challenge of Microsoft's entry into the dynamic and competitive movie industry. As technology and entertainment converge, Microsoft recognizes the strategic importance of establishing a foothold in the cinematic landscape. The real-world problem at hand involves navigating the complexities of the movie industry, understanding audience preferences, and optimizing content creation and distribution. Stakeholders in this endeavor include Microsoft executives, content creators, distributors, and end-users. By leveraging data analytics, market insights, and cutting-edge technology, this project aims to empower Microsoft to make informed decisions, tailor content to audience demands, and strategically position itself in the movie industry.

#### BUSINESS UNDERSTANDING
This project aims to generate insights and recommendations to the Microsoft company though Exploratory data analysis(EDA) in the current film industry giving insights on venturing into this industry. This project tends to analyze the trends and patterns associated with the current success rate of films and movies in box office examining factors such as budget(cost) of movie production, top-rated movies and more. This project tends to convert practical recommendations and insights to make more realistic and informed decision about the type of film to venture into, if it worth it and to the right target audience. These findings will be of great significance to the current stakeholders in getting to know what they are getting into and make informed decisions such as budget allocation or even potential risks

#### DATA UNDERSTANDING
For this project we used data from for files provided from different movie sites.
•	Box Office MojoLinks to an external site(https://www.boxofficemojo.com/).
•	IMDBLinks to an external site(https://www.imdb.com/).
•	Rotten TomatoesLinks to an external site(https://www.rottentomatoes.com/).
•	TheMovieDBLinks to an external site(https://www.themoviedb.org/).
•	The NumbersLinks to an external site(https://www.the-numbers.com/).

This data analysis of this project envelops diverse data from box office which draws its data from different movie sites such as IMDb, rotten tomatoes, the movie Db the numbers and many more. Files from these sites included ‘csv’, ’tsv’ and database file from IMDb .The dataset includes but to mention a few genre budget, movie gross, release dates, reviews, original title and popularity. These datasets will be crucial in identifying trends common in most successful movies including what the target audience preferences. The budget and gross is important because they measure the success rate in terms of finances and investments. Inclusion of original movie language may offer a good background and insight into regional preferences and success in the international market. Last but not least review will be crucial in determining the success rate of a movie in the long run. Descriptive statistics reveals the range and distribution of certain key features such as the budget cost and returns per region. The budget and gross will also be crucial and will be a determinant factor in realizing the success of this venture. However, this project also takes into inclusion limitations that come with venturing into this industry. This might include quality and incompleteness of the data being received from box office which does not predict future trends of the industry. Data from box office might be current and to make more informed appropriate decisions it requires one to have historical data to make more future decisions. Data privacy concerns might prove to be a limitation since peoples are more concerned with the ever changing technologies and might be worried about how their data is being utilized since we are using some of their reviews and ratings. The company should also guarantee compliance with regulations concerning controlling and gathering of information


#### Data Preparation

The project begun by including necessary libraries use to analyze and visualize the data.Libraries such as pandas, numpy,matplotlib and seaborn. For the IMDb database we connected to the database through sqlite3. Files from the movies sites we used pd.read(csv/tsv) to read data from them


Second Step was to check for the completeness of data in the columns before analysis of the data begins. From movie_info tsv file the file had quite a big number of missing values with currency, studio and box office columns displaying so. For this tsv file we were more interested in the ratings, genre and runtime columns and they had only a few missing values. For this file the best option was to drop the null values from the rows. Before dropping the total number of rows were 1560 and 12 columns. For better analysis we checked the total sum of null values from the rows then dropped the nul values
#checking for total null values
movie_info_df.isna().sum()


#dropping the null values
movie_info_df = movie_info_df.dropna()


### DATA ANALYSIS
The project analysis was curious to know what genre should we begin looking at from the vast number of genres available and which would be the best suitable genre for presentation to the company. The project checked the value count of movie genres and found out that drama genre was mainly watched genre followed closely by comedy then comedy and drama and drama and mystery.
![movies vs count graph](https://github.com/ed-gar-k/final-PH-repo/assets/109956677/2258562d-da6a-4292-9171-72af90ebda3e)


From this,findings the project suggests that microsoft should invest mostly in the top 5 genres for a start beginning with drama movie genre to be able to get viewers from the beginning of movie production.

From the analysis also the project tried to find out about other studios in the movie production business currently through value counts

![movie counts 2](https://github.com/ed-gar-k/Phase-1-project/assets/109956677/ebe89e95-8f9c-41c7-9c5a-e5cbda89529a)

From the graph we notice that the top studio was universal pictures with a count of 23 followed by paramount pictures with a count of 15. These two studios would be the two main competitors to Microsoft and more effort should be put to know why they are the most preferred studios.

From the file we also tried to find the average runtime of different movies

![runtime stats 2](https://github.com/ed-gar-k/Phase-1-project/assets/109956677/6aae6966-0f2d-4527-8d20-ae47bdfe7cc9)

This dataframe shows the runtime stats like the mean median and standard deviation. The maximum runtime minutes is 188 minutes while the minimum runtime is 67 minutes, The average runtime minutes is 106 minutes
25th Percentile (Q1): 93 minutes
This means that 25% of the movies in the dataset have a runtime of 93 minutes or les s. 50th Percentile (Q2 or Median): 105 minues
This is the middle value of the dataset when it is ordered. It separates the lower 50% of runtimes from the upper This means 50% of the movies have a runtime of 105 minutes or less, and the other 50% have a runtime of 105 minutes or more. 75th Percentile (Q3): 117 minutes
This means that 75% of the movies in the dataset have a runtime of 117 minutes 
Judging by this data, movies produced by microsoft should range between 90 minutes and 120 minutes or less.


In terms of ratings
Top rated R had 105,PG-13 had 77,PG – 38, NR-9

![rating graph](https://github.com/ed-gar-k/final-PH-repo/assets/109956677/0ff77275-b0de-4bae-83a8-a94d9135d6b9)

This dataset shows that a good number of movies are rated restricted meaning viewers should be over the ag of 17 or 18. A good number of target audience for movies are people aged above 18. Restricted movies are followed closely by PG-13 which means parents strongly cautioned and the movie might be appropriate for users aged below 13. Parental guidance rated movies is third meaning movie might not be suitable for children. This project data then suggests that a good number of movie watchers are mostly adultts and the company should invest more on Restricted movie but also shoul be able to invest in PG-13 rated movies to suit all audiences
##### Budget analysis
The project also tried to look at the budget of movie productions from previous years and estimate figures Microsoft should anticipate. First we get to find the international gross which is worldwide gross – domestic gross to know how much returns to movies get from the international audience.
![international gross](https://github.com/ed-gar-k/final-PH-repo/assets/109956677/300b5018-d78a-45e2-9c92-d1eb39a785b0)


 
From the international gross we then try to find the differences between the international gross to know the pattern involved. From the table it shows that alot of returns are from international audience. More movie marketing should also be done in the international market.

![scatter plots](https://github.com/ed-gar-k/final-PH-repo/assets/109956677/88f2a2b4-ab45-4b77-8aa0-5f0bfbdeaadc)

The above scatter graph shows the relation between domestic gross vs international gross and production budget against worldwide gross. This plot shows that an increase in domestic gross will influence an increase in international gross and production budget influences worlwide gross

The project then tries to estimate production budget, gross and profits as shown below

![profits](https://github.com/ed-gar-k/final-PH-repo/assets/109956677/782ce968-ab17-4885-bf3f-6fdb2c0d11c2)

From the table we can see that the estimated production for starting a movie would be figures close to $31,587,760 and profits would be close to $59,899,700 but does not those would be the actual profit figures but most movies make profits of up to $8,550,286 and more

![heatmaps](https://github.com/ed-gar-k/final-PH-repo/assets/109956677/a392a13f-1833-4ea4-ab2b-5cf1998f91e4)

#### number of votes against popularity and average rating
From the third file the project analyzed which included popularity, vote average and vote count. In terms of correlation of popularity vs vote average with a correlation co efficient of 1 indicates a perfect positive correlation. This means that as popularity increases, vote average in movies also increases. It indicates a strong positive relationship between popularity and vote average. Vote count vs vote average shows a correlation coefficient of 0.73 which indicates a strong positive correlation and suggests that as the vote count increases the vote average tends to increase but it is not a perfect correlation

![movie counts](https://github.com/ed-gar-k/final-PH-repo/assets/109956677/18b02522-d54a-48ff-aab1-8f250b3f9237)


![heatmaps](https://github.com/ed-gar-k/final-PH-repo/assets/109956677/a392a13f-1833-4ea4-ab2b-5cf1998f91e4)


From the movie info file the projects tries to find out which writes microsoft should try and collaborate with . From the value counts conducted the top most writer was Woody Allen with a total of 4 movies written followed by John Hughes with 3 and Jim Jarsmuch with 3 too . This project then goes ahead to suggest the three writers as a good potential start to write movies for Microsoft.
In the reviews file the project tries to find what ratings do most movies to be able to know the average rating Microsoft movies get. Most movies had a rating of 2/4 and ¾ this means Microsoft should anticipate ratings between 2 and 3 if they produce average movies. In terms of publishers, Reelings reviews was top followed by Patrick Nabbaro

From  the database the project mainly used 3 tables, movies basics movie akas and movie ratings. The first table we used  was movie basics to know what number of movies were produced in a certain year. From the result we notice that 2014 had the highest number of movies produced followed by 2013. The project results displayed then shows a gradual decrease of movies produced with 2023 having the least from the data we had.

![inception](https://github.com/ed-gar-k/final-PH-repo/assets/109956677/dbc01431-ecbf-4ede-9185-72a6ad559126)

From the movie ratings table the average rating and numvotes columns displayed in the scatter plot, we can see that alot of movies are mostly between 6 and 8 with a large number of movies being rated 7
![num votes and average rating](https://github.com/ed-gar-k/final-PH-repo/assets/109956677/6ff843b5-ca6d-42cc-852f-0344d01a642f)

![movie counts](https://github.com/ed-gar-k/final-PH-repo/assets/109956677/18b02522-d54a-48ff-aab1-8f250b3f9237)

From the movie ratings table the average rating and numvotes columns displayed in the scatter plot, we can see that alot of movies are mostly between 6 and 8 with a large number of movies being rated 7
![average rating](https://github.com/ed-gar-k/final-PH-repo/assets/109956677/595f8324-ac60-4f04-8c5a-e87b29d0fb34)

Inception movie was top movie with a high number of counts and an average rating of 8.8 while the dark knight rises had an average rating vote of 8.4. Microsoft should analyze these type of movie content to know what type of content fascinates the audience
![inception](https://github.com/ed-gar-k/final-PH-repo/assets/109956677/dbc01431-ecbf-4ede-9185-72a6ad559126)

#### correlation of average rating and vote count
![num votes and average rating](https://github.com/ed-gar-k/final-PH-repo/assets/109956677/6ff843b5-ca6d-42cc-852f-0344d01a642f)

From the above correlation map shows the relationship between average rating and number of vote counts
From the graph number of votes against average rating the correlation coefficient was 0.82. This is a positive correlation coefficient suggests that as average rating increases there is a tendency for number of votes to increase. 
This suggests a fairly consistent relationship between the two variables. 
When you observe a movie with higher rating there is a likelihood that it has received a higher number of votes

### Conclusion
From this analysis the project concludes that the company should not limit the production budget if the company want to register higher profits. Production budget influences the profits made from movies
Marketing of movies should be done worldwide more since a higher number of votes by the audience means the higher rating if the quality of the movie is high
The company should try and collaborate with top writers and directors because of their experience in the movie industry
More datasets should be analyzed before Microsoft joins the movie industry to ensure a good work is done on the movies.

