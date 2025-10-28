<H3>ENTER YOUR NAME : HYCINTH D</H3>
<H3>ENTER YOUR REGISTER NO: 212223240055</H3>
<H3>DATE:28-10-25</H3>
<H1 Align="center">Project Based Experiment<H1>
<H3>Objective:<H3>
Type your objective based on the question
<H3># Install required library if not already installed
# pip install pandas textblob

import pandas as pd
from textblob import TextBlob

# Step 1: Load your Facebook data
# Example: your data is stored in a CSV file with a 'Comment' column
data = pd.read_csv("facebook_data.csv")

# Step 2: Define a function to analyze sentiment
def get_sentiment(text):
    analysis = TextBlob(str(text))
    return analysis.sentiment.polarity

# Step 3: Apply the sentiment analysis
data["Sentiment_Score"] = data["Comment"].apply(get_sentiment)

# Step 4: Classify as Positive, Neutral, or Negative
data["Sentiment_Type"] = data["Sentiment_Score"].apply(
    lambda score: "Positive" if score > 0 else ("Negative" if score < 0 else "Neutral")
)

# Step 5: Filter only Positive feedback
positive_feedback = data[data["Sentiment_Type"] == "Positive"]

# Step 6: Display the positive feedback
print("Positive Feedback:")
print(positive_feedback[["Comment", "Sentiment_Score"]])

# Optional: Save filtered data to a new CSV
positive_feedback.to_csv("positive_feedback.csv", index=False)
print("\nFiltered positive feedback saved as 'positive_feedback.csv'")
</H3>

<H3>Output:</H3>
```
| Comment                          |
| -------------------------------- |
| I love this product!             |
| It’s okay, could be better.      |
| Terrible service, not happy.     |
| Absolutely wonderful experience! |
| Not worth the price.             |
| Great quality and fast delivery! |
```
<H3>Inference:</H3>
Write about your learning experience out of this project. (What you have learned)
Working on this project of performing sentiment analysis using Facebook data has been a valuable learning experience. I learned how to handle real-world social media data, preprocess it, and apply Natural Language Processing (NLP) techniques to extract insights from textual information.
Through this project, I gained practical experience in:
Data Handling with Pandas – importing, cleaning, and filtering large datasets effectively.
Sentiment Analysis with TextBlob – understanding how polarity scores are calculated and how text can be classified as positive, negative, or neutral.
Automation of Data Filtering – using conditions to extract and save only the required results (like positive feedback).
Data-Driven Decision Making – realizing how businesses can use sentiment data to understand customer opinions and improve products or services.
Python Programming Skills – improving my ability to write clear, modular code for real-world data analysis tasks.
