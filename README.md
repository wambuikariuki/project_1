Title is Genre Insights and Content Composition Analysis on an Entertainment Platform![image](https://github.com/wambuikariuki/project_1/assets/145265208/37c984a5-296e-4763-aa80-0f254f6ab98d)
#Project overview 
In this project, I aim to provide valuable insights to Microsoft as they embark on establishing a new movie studio. Leveraging on exploratory data analysis techniques, we will delve into various movie datasets to understand current trends in the box office. By examining factors such as movie genres, ratings, and box office performance, we will generate actionable recommendations to guide Microsoft in making informed decisions regarding their movie production strategy
#Business understanding
Microsoft recognizes the growing importance of original video content in the entertainment industry and seeks to capitalize on this trend by venturing into movie production. However, lacking prior experience in the film industry, Microsoft aims to gain insights into the types of films that resonate well with audiences and perform strongly at the box office. By understanding market trends and audience preferences, Microsoft can strategically position themselves to maximize the success of their movie ventures
![image](https://github.com/wambuikariuki/project_1/assets/145265208/cdbbbf90-9c92-4030-86f1-a9ca29d0a362)
#problem statement
Microsoft is entering the movie production industry without prior expertise and seeks guidance on the types of films that are currently successful at the box office. The challenge lies in analyzing extensive movie data to identify key trends and translate these findings into actionable insights that will inform Microsoft's movie production strategy
![image](https://github.com/wambuikariuki/project_1/assets/145265208/ca75b3a4-2a0f-4bdf-be08-592da6efb6f1)
#four objectives
1. Evaluate the Relationship Between IMDb Ratings and Audience Engagement.
2. Identify High-Performing Titles Across Different Categories
3. Analyze Category Contributions to Overall Ratings and Engagement
4. Detect Patterns or Trends in Audience Preferences


#code snipet
# Create a histogram using seaborn to show distribution of IMDb ratings
plt.figure(figsize=(12, 8))
sns.histplot(project_1['averagerating'], bins=30, kde=True, color='skyblue')
plt.title('Distribution of IMDb Ratings')
plt.xlabel('IMDb Rating')
plt.ylabel('Frequency')
plt.show()

##IMDb ratings vs number of votes
plt.figure(figsize=(12, 8))
sns.scatterplot(x='numvotes', y='averagerating', data=project_1, hue='category', alpha=0.7)
plt.title('Bivariate Analysis: IMDb Ratings vs Number of Votes')
plt.xlabel('Number of Votes')
plt.ylabel('IMDb Rating')
plt.legend(title='Category', bbox_to_anchor=(1.05, 1), loc='upper left')
plt.show()
#percentage occurence
#count occurence of each genre
genre_counts = pd.Series({'Action': 30, 'Comedy': 20, 'Drama': 25, 'Thriller': 15, 'Horror': 10})

# Define explode list with the same length as genre_counts
explode = [0.1] * len(genre_counts)

# Define colors
colors = plt.cm.Set3.colors  # Use Set3 color map for better visibility

# Plot the pie chart
plt.pie(genre_counts, labels=genre_counts.index, autopct='%1.1f%%', startangle=90, colors=colors, explode=explode)

# Draw a circle in the center of the pie to make it look like a donut chart
centre_circle = plt.Circle((0,0),0.70,fc='white')
fig = plt.gcf()
fig.gca().add_artist(centre_circle)

plt.axis('equal')  # Equal aspect ratio ensures that pie is drawn as a circle.
plt.show()
## Scatter plot: averagerating vs. numvotes
plt.figure(figsize=(10, 6))
sns.scatterplot(x='numvotes', y='averagerating', data=project_1, alpha=0.5)
plt.title('Scatter Plot: Average Rating vs. Number of Votes')
plt.xlabel('Number of Votes')
plt.ylabel('Average Rating')
plt.show()
#RECOMMENDATIONS
Offer Variety: Show different types of movies to attract more people.
Show Popular Movies: Focus on the types of movies that people like the most.
Keep Up with Trends: Stay updated on what kinds of movies are becoming popular.
Pick Movies People Like: Choose movies that match what people in the area like to watch.
Include Everyone: Show movies that everyone can enjoy, with diverse actors and stories

