#  AI Writer with Text Summarization

An intelligent web application that summarizes large articles using NLP models from Hugging Face. It simplifies lengthy content into concise summaries and provides insights like word count and readability score.

##  Objective  
Generate concise, high-quality summaries from long-form text using transformer-based NLP models.

---

##  Features

-  Input long-form text  
- Summarization using **BART** / **T5** transformer models  
-  Word count &  readability score  
-  Optional summary history  
-  Flask-based web interface  
---

##  Tools & Technologies

- Hugging Face Transformers  
- Flask  
- Google Colab / VS Code  
- Python (Transformers, Flask, TextStat)  

---

##  Model Architecture

###  BART (Bidirectional and Auto-Regressive Transformers)

- Encoder-Decoder structure  
- Combines BERT (bidirectional) and GPT (auto-regressive)  
- Pretrained on denoising autoencoding and sequence-to-sequence tasks  

###  T5 (Text-to-Text Transfer Transformer)

- Treats all NLP tasks as text-to-text  
- Trained on C4 dataset  
- Summarization via input format: `"summarize: <text>"`  

---
# Sample Usage  
from textSummarizer.pipeline import TextSummarizer
if input_text.strip():
    summary = summarizer(input_text, max_length=130, min_length=30, do_sample=False)[0]['summary_text']
    readability = flesch_reading_ease(summary)
    word_count = len(summary.split())

    print("\nSummary:\n", summary)
    print("\nSummary Word Count:", word_count)
    print("Readability Score:", readability)
else:
    print("No input detected. Please paste a valid text.")text-summarization-project/
│
# Project Structure 
├── app/
│   └── main.py                  # Flask backend
│
├── textSummarizer/
│   ├── constants.py             # Paths and model names
│   ├── pipeline.py              # Summarizer logic
│   └── utils/
│       └── common.py            # Helper functions
│
├── static/                      # CSS, JS
├── templates/                   # HTML templates
├── requirements.txt
└── README.md

---
# Result

| **Metric**         | **Value**                |
| ------------------ | ------------------------ |
| **Input Length**   | 2000 words               |
| **Summary Length** | \~80–100 words           |
| **Readability**    | Grade 6–8 (Good clarity) |
| **Inference Time** | \~3–5 seconds            |
| **Models Used**    | BART, T5                 |

# Conclusion 
This project showcases the practical application of state-of-the-art Natural Language Processing (NLP) to automate summarization tasks using advanced transformer models like BART and T5. By integrating Hugging Face's pretrained models with a Flask-based web interface, we deliver a powerful, easy-to-use application tailored for researchers, students, content creators, and professionals who deal with large amounts of text.

The summarizer effectively reduces reading time and enhances content comprehension by generating concise, meaningful summaries. It also provides helpful metrics like word count and readability score for better content assessment.

# License
This project is licensed under the MIT License.


