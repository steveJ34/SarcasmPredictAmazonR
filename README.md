## Sarcasm Prediction using RStudio 

### Research Purpose
The aim of the research is to investigate some of distinct features of sarcastic reviews, using NPL techniques, such as tf-idf and sentiment analysis. After cleaning and pre-processing, models are used to explore the optimal way for predicting sarcasm in reviews. The main interest is to discover distinctive features of sarcasm that would help enable to establish a robust method of sarcasm prediction.

### Data and Preparation 
The data was sourced from the following GitHub repo https://github.com/ef2020/SarcasmAmazonReviewsCorpus/wiki. It contains a collection of ironic/sarcastic and regular (non-sarcastic) reviews. The reviews included into the Corpus come from www.Amazon.com.

For each review, information such as the product description, the number of stars that was assigned to the product by its authors, etc. is provided. The used data originally was stored in two sets of txt files, described below:

Ironic: the directory contains all the ironic/sarcastic Amazon product reviews that were submitted on Step 1 of the corpus collection procedure and confirmed as ironic on Step 2 by both majority voting and label quality control algorithm.
Regular: contains all the regular Amazon product reviews that were submitted on Step 1 of the corpus collection procedure and confirmed as regular on Step 2 by both majority voting and label quality control algorithm.

The original data was cleaned and re-structured to tidy format. After that, it was stripped of all the stopwords. The unnest_token() function was used to unnest the titles, product description and reviews, using different tokens, such as words, ngrams and sentences. Words and bi-grams were used as tokens for EDA and visualizations. For sarcasm predictions, the main tokens were sentences. After unnesting the tokens one by one, the approximate sentiment (polarity) of tokens was calculated for each token using the unnest_by() function from the “sentimentr” package. At the end the text was re-constructed and the approximate sentiments were averaged. The average sentiments of the reviews were used as explanatory variables in the models.


