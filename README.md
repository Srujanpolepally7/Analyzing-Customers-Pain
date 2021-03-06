# Analyzing-Customers-Pain

The project is divided into two parts.

The first part is the web scraping part where extractions of reviews for the top healthcare industries in USA are done using web scraping libraries available in Python.

The second part is the Sentiment Analysis part where the data (text reviews) extracted from scraping is cleaned and processed in order to extract various features from the dataset and then apply sentiment analysis to obtain key insights like – which company has got the most negative/positive reviews, what are the topics of liking/disliking among the customers, most frequently used words in the review etc.

## PROBLEM STATEMENT

Online product/service reviews are a great source of information for consumers. From the seller’s point of view, online reviews can be used to record the consumer’s feedback on the products or services they are selling. However, since these online reviews are quite often overwhelming in terms of numbers and information, an intelligent system, capable of finding key insights (topics) from these reviews, will be of great help for both the consumers and the sellers. This project will serve two purposes:

• Enable consumers to quickly extract the key topics covered by the reviews without having to go through all of them

• Help the sellers/retailers get consumer feedback in the form of topics (extracted from the consumer reviews)

## SCRAPING TASK

Steps to scrape data

We will first extract the reviews, rating from the first page of the website and store it in separate lists since the URL for this page is unique.

Using a ‘for loop’ we request the other pages and extract the data. This extracted data gets stored in a 2D list where each list contains reviews & corresponding ratings from different pages.

Place the data from 2D list to 1D list containing all the reviews in one list and their corresponding rating in a different list. Then merge the review, rating list of first page and other pages. Finally create a dataframe with columns ‘Reviews’, ‘Rating’ & ‘Company’

A similar kind of data frame is created for other companies by following the same steps explained previously.

Then we concatenate the data frames for other companies and export it as csv. This csv file is then used for the ‘Sentiment Analysis’ of reviews by applying the concepts of Natural Language Processing (NLP)

## SENTIMENT ANALYSIS

- Importing the dataset obtained after scraping project – dataset.csv

- View the dataset to get basic insights – shape, descriptive statistics, dataset head

- Add a column of ‘text length’ for each review to check if it can be a helpful feature for our model

- For better decision-making visualize the distribution of text-length for each rating using histograms and box-plots

- Create a new dataset which contains data only with rating ‘1’ (negative) or ‘5’ (positive)

Text Pre-processing

- Convert the ratings into binary format : Rating 5="1" , Rating 1="0“ using label encoder

- Using regular expressions replace text like email addresses with ‘emailaddr’ and similarly for others

- Remove stopwords and then lemmatize each review text

- Find the most common and rare words

- Create a new dataset with the processed reviews and corresponding encoded rating for feature extraction

Feature Engineering

- Use Vader to find the polarity score for each review of our pre-processed dataset

- Adding ‘word-count’ & ‘character-count’ columns to the dataset to see the reduction in dataset

- Add TF-IDF columns for every word and document

- Print the wordcloud from available reviews

- Find the highest sentiment positive reviews

- Plot sentiment distribution for positive and negative reviews
