# Assignment-4_-Data-Visualization-with-Python-R--Netflix-Data-
##Data Visualization _Netflix Data 
The Assignment involves using python and R programming to visualise the Netfrix data as per below steps
### 1. Data Preparation:
   I downloaded and saved the Netflix data as a  Netflix_shows_movies CSV file. 

     df = pd.read_csv('Netflix_shows_movies.csv')  # This allows one to read the PDF file 
     print(df)                                     #This allows one to view the file 

### 2.Data Cleaning:
There were quite a number of missing values in the director/cast/country/date and rating columns and i used fillna function to fill in the missing values with N/A. Deleting the missing values meant that other columns with data will be lost thus losing some information that is necessary in our data analysis.

df['director'].fillna('N/A',inplace=True)     #This function replaces missing values in the columns mentioned with NA
print(df.isnull().sum())                      #This functoin show us if there are still missing values in the data              


### 3.Data Exploration:
Exploring our data to get an understanding of tha data set.

print(df.info())     # Provides us with the information about the data set like the column names, Datatype(integers/objects/floats), nullnull count

print(df.describe()) # Provides a sumary of the data lime the mean, mode, medial, quartiles, standard deviation the max and min values 

df.head(10)          #Shows the first 10 rows of the data 


### 4.Data Visualization:
# Python:Most watched genres.
This code represents a bar chart 

plt.figure(figsize=(12, 6))
top_genres = df['listed_in'].value_counts().head(10)
top_genres.plot(kind='barh', color='#b20710',alpha=0.8)  #The chart is a bar graph , color red with the a color intensity of 0.8
plt.title('Top 10 Most Watched Genres on Netflix')   #Tile of the chart 
plt.xlabel('Number of Titles')       #On the X -axis : Number of titles
plt.ylabel('Genre')                  #On the Y -axis : Genre
plt.show()  

# Python:Ratings Distributions
This code represents a bar chart

plt.figure(figsize=(8, 6))
sns.countplot(x='rating', data=df, palette='pastel')    # Different colors 
plt.title('Distribution of Ratings on Netflix')
plt.xlabel('Rating')
plt.ylabel('Number of Titles')
plt.show()


### R Integration:
In R Programming this is the code for the 2 graphs as represente in Python 
1. We installed the ggplot 2 library package necessary for plotting in R

install.packages("ggplot2")
library(ggplot2)
df <- read.csv("C://Users//DORIS//Netflix_shows_movies.csv")   #Loading the dataset
str(df)
head(df)

# Visualization 1: Most Watched Genres
ggplot(df, aes(x = listed_in)) +
  geom_bar(stat = "count", fill = "Red") +
  theme_minimal() +
  labs(title = "Most Watched Genres on Netflix", x = "Genre", y = "Number of Titles")

# Visualization 2: Ratings Distribution
ggplot(df, aes(x = rating, fill = rating)) +
  geom_bar() +
  theme_minimal() +
  labs(title = "Ratings Distribution on Netflix", x = "Rating", y = "Number of Titles")


Challenges:
1. The Netflix data was a csv file so unzipping it was somewhat a challenge.
2. Alot of research in gettng to understand more about the topic in both R and Python hence time consuming.

Lessons learnt
1. I need to do alot more practive in data visualization since there are many charts and packages in both R and Python that are key when working on data visualization.

| [top](#smileys--emotion) | :slightly_smiling_face: | `:slightly_smiling_face:` | :upside_down_face: | `:upside_down_face:` | [top](#table-of-contents) |


