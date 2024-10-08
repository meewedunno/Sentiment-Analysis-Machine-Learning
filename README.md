# ELSA SPEAK - SENTIMENT ANALYSIS FROM GOOGLE STORE REVIEWS
## Problem Statement and Data Description
"ELSA Speak" is a mobile application designed for English learning through interactive speech recognition and pronunciation practice. As the app's popularity grows, understanding user sentiments from their reviews on the Google Play Store becomes crucial for several reasons.

1. **User Experience Enhancement:** User reviews often contain valuable insights into users' experiences with the app. Sentiment analysis can uncover sentiments expressed by users, helping identify areas of improvement or aspects users appreciate.
2. **Feature Prioritization:** By analyzing sentiments expressed in reviews, it becomes possible to prioritize features that users highly appreciate or dislike. This aids in focusing development efforts on areas that matter most to users.
3. **Business Decision Making:** Sentiment analysis provides actionable insights for business decisions. Positive sentiments can be leveraged for marketing and promotions, while negative sentiments can guide strategic improvements.

### Objective: Given a review, determine whether the review is positive or negative.
A rating of 4 or 5 can be cosnidered as a positive review. A rating of 1 or 2 can be considered as negative one. A review of rating 3 is considered neutral and such reviews are ignored from our analysis. This is an approximate and proxy way of determining the polarity (positivity/negativity) of a review.

### Data
The raw dataset about reviews on ELSA Speak scaped from Google Play Store contains 49451 rows and 11 columns.
**The description for each column in the dataset:**
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

