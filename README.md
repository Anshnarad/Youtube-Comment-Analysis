# Youtube-Comment-Analysis
Basic sentiment analysis of comments on a youtube video using a builtin python package "Vader Lexicon" and "Youtube Data API".

# How it is made
I have simply used "Youtube Data API" which is available on "Google Developers Console" to scrap youtube comments of a particular video and download them in a CSV format. Then I have made use of python library called "NLTK" (Natural Language Toolkit), a platform for building python programs to work with Human language data. More specifically, what I have used is called VADER (Valence Aware Dictionary and Sentiment Reasoner) which is a lexicon and rule-based sentiment analysis tool that is specifically attuned to sentiments expressed on social media. I have combined this vader lexicon and youtube data api to give a machine generated report on sentiments of comments that are posted (Expressed) on a particular video.

# Scoring Procedure
The basic idea behind sentiment analysis using vader lexicon is that it contains a dictionary of words with some value assigned to it. Eg a word like **"Good"** or **"Amazing"** would have some **Positive value** assigned to it and a word like **"Bad"** or **"sad"** would have a **Negative value** assigned to it. So what I did is that I made a program that reads through the lines from a CSV file that contains all the comments on a particular youtube video and then calculate `Compound Score` for each line and label it according to the following relation:-

1. `Positive sentiment: compound score >= 0.05`
2. `Neutral sentiment : (compound score > -0.05) and (compound score < 0.05)`
3. `Negative sentiment: compound score <= -0.05`

# Applications
It can be used by youtube content creators and channel owners to analyse the response of audience viewing and commenting on their videos. Since there are millions of comments made on youtube each day it can become difficult to read all the comments on a video, but since it is also important to know the feedback and what people think of a video or a particular content this can be used as youtube report to know if the comments on a video are **Positive, Negative or Neutral**. This is made interactive and easy to understand by concluding the report with **final result** of all the calculations and a **piechart** containing info about percentage of `positive`, `negative` and `neutral` comments.

# To run this
You will have to install some libraries. `Run:`
1. `pip install vaderSentiment`
2. `pip install httplib2`
3. `pip install google-api-python-client`
4. `pip install csv`
5. `pip install oauth2client`

**You will also have to set up Google Cloud:**
1. Go to "Google Developers Console".
2. Enable "Youtube Data API".
3. Create Credentials.
4. Download the credentials to `client_secrets.json`.

**Running the program**

Just type in your terminal `python3 youcomment{main file}.py --videoid=fc93EBfcb7w{example videoid}` and press enter.



