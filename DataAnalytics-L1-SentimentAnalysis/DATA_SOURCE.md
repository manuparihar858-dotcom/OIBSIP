# Dataset Source

Dataset: TweetEval — Sentiment

Task: sentiment classification

Classes:
- negative
- neutral
- positive

The notebook loads the dataset at runtime using the Hugging Face `datasets` library:

`load_dataset("tweet_eval", "sentiment")`

The raw dataset is not committed to this repository. The dataset is retrieved when the notebook is executed.

Reference:
TweetEval benchmark: https://github.com/cardiffnlp/tweeteval
