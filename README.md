# NLP WebScraping And Sentiment Analysis
### Task:
  1. To scrape reviews from Amazon Website for the product 'Fastack Ladies Watch'
  2. Perform Sentiment Ananlysis and Categorize Reviews into 'Positive' and 'Negative'
### Dataset:
  Scrapped text data from Amazon
  
### Approach:
#### Web Scraping using BeautifulSoup
  1. Imported BeautifulSoup and requests
  2. Made a dictionary that contains user-agent and referer data. This facilitates scraping without obstructions
  3. As the reviews are uncountable, performed review scrappings only for the first page products
     - Acquired the list of items on the first page
     - Discovered their data-asin number
     - Acquired all review links using data-asin
  4. Gathered up to 100 product reviews
  5. Saved reviews in a dataframe
  6. total of 12251 reviews were scraped
    
#### Sentiment Analysis
Performed Sentiment analysis using VADER Lexican Approach
  1. Cleaned the data for Nan and empty values
  2. Imported SentimentIntensityAnalyzer from nltk vader_lexican
  3. Calculated polarity_scores of each review using SentimentIntensityAnalyzer object. polarity_scores consists of pos, neu, neg, compound values
  4. Extract compound values of each Review
  5. Mark 'pos' for positive compound values and 'neg' for negative compound values. 'pos' indicates positive toned reviews and 'neg' indicates negative toned reviews
  6. The review for 'Fastrack Ladies Watch' has 10537 positive reviews and 1444 negative reviews
  
#### Model Evaluation
Performed Model Evaluation using a pickled reviews model 
  1. Loaded a pickled model
     - It is a text classification model
     - Evaluated with original values and scored 92% accuracy
     - Performs TF-IDF vectorization and LinearSVC modelling
  2. Made predictions for the amazon reviews
  3. Evaluated resuls using accuracy_score
  4. Obtained accuracy of 77%
