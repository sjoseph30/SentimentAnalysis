# 🩺 Sentiment Analysis on Patient Reviews

This project performs sentiment analysis on patient-written reviews using three different NLP models: **VADER**, **BERT**, and **Flair**. The script reads a CSV file containing free-text reviews, computes sentiment scores using each model, and exports the results to a new file.

---

## 🔧 Requirements

Make sure you have Python 3.7 or later. Then install the required libraries:

```bash
pip install pandas torch transformers flair vaderSentiment

📁 Input
The script expects a CSV file named File.csv in the same directory. It should contain at least one column:

Review: The text of the patient review

📊 Output
The script outputs a CSV file named Sentiment_Results.csv with the following columns:

Review: Original review text

VADER_Score: Compound sentiment score from the VADER model (range: -1 to 1)

BERT_Score: Sentiment score from BERT (positive value for positive sentiment, negative for negative sentiment)

Flair_Score: Sentiment score from Flair (positive or negative based on classification)

🧠 Models Used
Model	Description	Domain
VADER	Rule-based lexicon model for general sentiment analysis	General-purpose
BERT (distilbert-base-uncased-finetuned-sst-2-english)	Transformer model fine-tuned on SST-2 (Stanford Sentiment Treebank)	General-purpose
Flair (en-sentiment)	RNN-based model trained on IMDB, Amazon, and Yelp reviews	General-purpose

Note: These models were not fine-tuned on healthcare-specific data. This may limit performance when interpreting clinical sentiment or patient emotions in medical contexts.

▶️ How to Run
Simply run the Python script:

bash
Copy
Edit
python sentiment_analysis.py
Make sure the File.csv input file is present in the same directory.

📌 Limitations
General-purpose models may miss healthcare-specific context or medical nuance.

Empty or missing review fields are automatically skipped.

VADER, being lexicon-based, may struggle with sarcasm or complex sentence structures.

🔮 Future Work
Fine-tune BERT or Flair models on healthcare-related review data (e.g., Healthgrades, RateMDs).

Explore domain-adapted models like:

BioBERT: Pretrained on PubMed abstracts

ClinicalBERT: Pretrained on MIMIC-III clinical notes

Evaluate model performance using labeled clinical sentiment datasets.

📂 Example Output (Preview)
Review	VADER_Score	BERT_Score	Flair_Score
"Dr. Smith was amazing and attentive."	0.92	0.99	0.98
"Waited over an hour. Very rude staff."	-0.71	-0.96	-0.87

👤 Author
Stanley Joseph
Medical College of Georgia
Augusta, GA
