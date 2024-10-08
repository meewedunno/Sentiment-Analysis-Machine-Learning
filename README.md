# ELSA SPEAK - SENTIMENT ANALYSIS FROM GOOGLE STORE REVIEWS
## Problem Statement and Data Description
"ELSA Speak" is a mobile application designed for English learning through interactive speech recognition and pronunciation practice. As the app's popularity grows, understanding user sentiments from their reviews on the Google Play Store becomes crucial for several reasons.

1. **User Experience Enhancement:** User reviews often contain valuable insights into users' experiences with the app. Sentiment analysis can uncover sentiments expressed by users, helping identify areas of improvement or aspects users appreciate.
2. **Feature Prioritization:** Analyzing sentiments expressed in reviews makes it possible to prioritize features that users highly appreciate or dislike. This aids in focusing development efforts on areas that matter most to users.
3. **Business Decision Making:** Sentiment analysis provides actionable insights for business decisions. Positive sentiments can be leveraged for marketing and promotions, while negative sentiments can guide strategic improvements.

### Objective: Given a review, determine whether the review is positive or negative.
A rating of 4 or 5 can be considered as a positive review. A rating of 1 or 2 can be considered a negative one. A review of rating 3 is considered neutral and such reviews are ignored from our analysis. This is an approximate and proxy way of determining the polarity (positivity/negativity) of a review.

### Data
The raw dataset about reviews on ELSA Speak scaped from Google Play Store contains 49451 rows and 11 columns. The description for each column in the dataset:
- **reviewId:** unique identifier
- **userName:** Name of a User
- **userImage:** Profile image that a user has
- **content:** The comments made by a user
- **score:** Rating between 1 to 5
- **thumbsUpCount:** Number of thumbs up received by a person finding this content helpful
- **reviewCreatedVersion:** Version number on which the review is created
- **at:** The time that the review created
- **replyContent:** Reply to the comment by the Company
- **repliedAt:** Date and time of the above reply
- **appVersion:** Version of the app

## Exploratory Data Analysis
From Q1 2020, it recorded a remarkable growth in the number of reviews on ELSA Speak, especially positive reviews, showing increasing public attention since its founding in 2015. Over a period of time, reviews with positive emotions were consistently higher than negative emotions. The number of positive comments peaked in January 2022 with 1865 reviews. However, since then, positive comments witnessed a downward trend, almost equal to the number of negative comments in recent.
<img width="779" alt="image" src="https://github.com/user-attachments/assets/29e36592-60c5-41cd-bdb8-ba9534f99a2b">

 ### Popular words in reviews
 **Positive reviews**
 
 <img width="776" alt="image" src="https://github.com/user-attachments/assets/a663cb48-2816-4b37-b3be-c1cf5f9e3bc8">
 
 **Wordcloud of positive reviews**
 
 <img width="563" alt="image" src="https://github.com/user-attachments/assets/52a1b080-95fd-4af6-95d8-3137e11f2b9a">
 
 **Negative reviews**
 
 <img width="765" alt="image" src="https://github.com/user-attachments/assets/2cff2947-06fb-4698-b3fe-ad74d8219016">
 
  **Wordcloud of negative reviews**
  
<img width="543" alt="image" src="https://github.com/user-attachments/assets/59c0a7bf-b9a8-4cc4-855c-229597fc1eb3">

A look at the popular words in positive (4-5 stars) and negative (1-2 stars) reviews shows that both positive and negative reviews share 
many popular words, such as "good", "nice", "app", and "english". The words "recommend", "improv", and "thank" are indicative of positive reviews, while negative reviews contain words such as "bad", "money", and "subscript" but these distinguishing words appear less frequently than shared popular words with positive reviews. Looking at the two heat maps, while buzzwords related to positive reviews tend to fade away, negative reviews gradually appear to be concerned about "free".

## Building a Model
As our main goal is to predict whether a review is positive or negative, so for that we need an appropriate classifier and hence we use RandomForestClassifier for this. In machine learning, computers cannot understand natural languages directly but can only understand languages when they are represented in the form of vector space. There are many methods to represent text into a vector matrix, including traditional ways such as Bag of Words, TF-IDF model, topic model or improved ways such as Word2Vec, GloVe, FastTex models. In this project, we apply two methods, Bag of Words (BOW) and TF-IDF, to do featurization before applying Random Forest Clasification.

<img width="755" alt="image" src="https://github.com/user-attachments/assets/fc430a6c-91ca-43ec-8607-91f2377ada2b">

From the above table we conclude that TFIDF in Random Forest with a optimal Depth of 60 and optimal estimator of 400 have the higher AUC score (74.33%) while BOW has higher accuracy rate in Confusion Matrix of (93%).

**Feature Importance on BOW**

<img width="713" alt="image" src="https://github.com/user-attachments/assets/a49a12ae-7ee7-4288-881c-0fb02ced62e9">

<img width="833" alt="image" src="https://github.com/user-attachments/assets/34d2d394-868c-41d6-a9dd-eeca0bcec028">

**Feature Importance on TFIDF**

<img width="676" alt="image" src="https://github.com/user-attachments/assets/cda3bc1e-cefb-4b15-bd86-4610f4c9ab9c">

<img width="796" alt="image" src="https://github.com/user-attachments/assets/722cfe35-e236-48c3-8ec4-cecb4a1efc90">

From the feature importance of both two featurization methods, it indicates the users show a decent interest on "free".


