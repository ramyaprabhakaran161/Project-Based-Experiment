<H3>NAME:RAMYA P</H3>
<H3>REGISTER NO:212223230168</H3>
<H3>DATE:08-08-26</H3>
<H1 Align="center">Project Based Experiment<H1>
    
<H3>Objective:<H3>
To analyze the sentiment of Facebook comments using Natural Language Processing (NLP) and TextBlob, classify them as Positive, Negative, or Neutral, count the occurrences of a specific name, and visualize the sentiment distribution.
    
<H3>Program:</H3>
```
Step 1: Import Libraries

import pandas as pd
from textblob import TextBlob
import matplotlib.pyplot as plt

Step 2:Load Facebook Data

data = pd.read_excel("FacebookPosts.xlsx")

print(data.head())
print(data.columns)

Step 3: Create Sentiment Function

def get_sentiment(text):
    analysis = TextBlob(str(text))
    
    if analysis.sentiment.polarity > 0:
        return "Positive"
    elif analysis.sentiment.polarity < 0:
        return "Negative"
    else:
        return "Neutral"

Step 4: Perform Sentiment Analysis

data['Sentiment'] = data['Timeline'].apply(get_sentiment)

print(data)

Step 5: Count Sentiments

sentiment_counts = data['Sentiment'].value_counts()

print(sentiment_counts)

This shows the number of positive, negative, and neutral comments.
Step 6: Count Occurrences of Your Name

name = "Ramya"

count = data['Timeline'].str.lower().str.count(name.lower()).sum()

print("Number of occurrences of", name, ":", count)

Step 7: Visualize Sentiment

plt.bar(sentiment_counts.index, sentiment_counts.values)
plt.title("Facebook Comments Sentiment Distribution")
plt.xlabel("Sentiment")
plt.ylabel("Number of Comments")
plt.show()
```
<H3>Output:</H3>
<img width="882" height="585" alt="image" src="https://github.com/user-attachments/assets/d96a75ef-9992-4861-9349-b6d88a905b0f" />

<H3>Inference:</H3>
The experiment successfully analyzed Facebook comments using TextBlob and classified them into Positive, Negative, and Neutral sentiments. The sentiment counts and graph help understand the overall emotional response of users. The occurrence count also helps identify how frequently a particular name appears in the extracted Facebook data.
