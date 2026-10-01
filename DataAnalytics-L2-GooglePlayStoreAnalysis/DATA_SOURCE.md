# Dataset Source

The project follows the Oasis Infobyte task sheet recommendation to use the public Google Play Store datasets commonly distributed through Kaggle.

Expected files:

1. `googleplaystore.csv`
   - Google Play Store app metadata
   - Typical columns include App, Category, Rating, Reviews, Size, Installs, Type, Price, etc.

2. `googleplaystore_user_reviews.csv`
   - User reviews associated with Play Store apps
   - Typical columns include App, Translated_Review, Sentiment, Sentiment_Polarity and Sentiment_Subjectivity.

Search reference from the internship task sheet:
- "Google Play Store dataset" on Kaggle
- Dataset title commonly distributed as "Google Play Store Apps"
- User review dataset commonly distributed alongside it as "Google Play Store User Reviews"

The raw CSV files are not embedded in this repository. Download them separately and place them beside the notebook before running it.

The notebook performs its own sentiment classification with VADER rather than relying on the dataset's pre-existing sentiment label.
