# Gender Bias in Book Reviews: Analyzing the Influence of Author Gender on Review Language and Ratings

This project explores the hypothesis that the perceived gender of a book's author impacts the language used in reviews and the ratings given. Specifically, we aim to investigate whether female authors are subject to harsher critiques than male authors.

## Research Questions
We focus on the following key research questions:
* **Do reviews of books written by female authors express more negative sentiment than those of books written by male authors, even when the star ratings are similar?**
* **Can the gender of a book's author be predicted based solely on sentiment score or star rating, or a combination of both?**

## Dataset and Methodology
The dataset used for analysis is a collection of **Goodreads book reviews**, containing information on over **2 million books and 800,000 authors**, categorized by gender and genre. We focused on **books with single authors** to clearly assign gender.

### Steps Involved:
1. **Data Preprocessing:**
   - Tokenized the reviews and assigned gender to authors. We recognize that this gender classification is based on reader perceptions and may be biased due to limitations of the classifier, especially with non-Western and non-binary names.
   
2. **Data Filtering:**
   - Excluded reviews shorter than 100 characters and books with fewer than 10 reviews.
   - Books with multiple authors were removed to ensure clear attribution of perceived gender.

3. **Sentiment Analysis:**
   - Sentiment scores were assigned to reviews using an R library that calculates the ratio of positive to negative words. This approach, while simple, may not capture more nuanced expressions such as sarcasm or informal language.

4. **Statistical Analysis:**
  - Model 1: Rating as a function of gender

    - Type of Regression: Proportional odds or ordinal logistic regression
    - Findings: Books by male authors received higher ratings (about 0.5 stars more) than books by female authors.
  
  - Model 2: Gender as a function of sentiment score

    - Type of Regression: Binomial regression (brui family)
    - Findings: Higher sentiment scores in reviews were more likely to be associated with books by male authors.
  
  - Model 3: Sentiment score as a function of rating and gender

    - Type of Regression: Beta regression
    - Findings: For male authors, higher ratings correlated with more positive sentiment. For female authors, reviews remained more negative even
      with higher ratings.
  
  - Model 4: Rating as a function of gender and sentiment score
    - Type of Regression: Proportional odds logistic regression
    - Findings: Sentiment score had little predictive value for ratings of female-authored books, while there was a weak positive association   between sentiment and higher ratings for male authors

## Key Findings:
* **Higher Average Ratings for Male Authors:** Books by male authors received higher average star ratings compared to books by female authors.
* **More Positive Sentiment for Male Authors:** Reviews of male-authored books generally had more positive sentiment.
* **Negative Sentiment for Female Authors:** Reviews of female-authored books were more likely to include negative language, even when ratings were higher.
* **Weak Correlation Between Sentiment and Ratings for Female Authors:** Sentiment scores were not a strong predictor of ratings for female authors, while positive sentiment showed a weak association with higher ratings for male authors.

## Limitations:
* The **gender classifier** used in this study may introduce biases, particularly with non-Western and non-binary names.
* The **sentiment analysis** method employed may not fully capture nuances such as sarcasm or informal language, which can affect the accuracy of sentiment scores.
* This study primarily focused on **poetry**. Future research should consider other genres to provide a broader understanding of potential biases.
