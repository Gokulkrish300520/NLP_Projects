#Tokenize and Tag Text

## Overview

This notebook demonstrates various techniques for tokenizing and tagging text using Python's NLTK and spaCy libraries. The goal is to explore different methods for breaking down text into words and sentences, as well as removing stop words.

## Table of Contents

- [Introduction](#introduction)
- [Setup](#setup)
- [Tokenization Techniques](#tokenization-techniques)
  - [Word Tokenization with NLTK](#word-tokenization-with-nltk)
  - [Tweet Tokenization with NLTK](#tweet-tokenization-with-nltk)
  - [Sentence Tokenization with NLTK](#sentence-tokenization-with-nltk)
  - [Removing Stop Words with NLTK](#removing-stop-words-with-nltk)
  - [Word Tokenization with spaCy](#word-tokenization-with-spacy)
  - [Sentence Tokenization with spaCy](#sentence-tokenization-with-spacy)
- [Conclusion](#conclusion)

## Introduction

Tokenization is the process of breaking down text into smaller units, such as words or sentences. This is a crucial step in natural language processing (NLP) as it prepares the text for further analysis. This notebook explores various tokenization methods using two popular NLP libraries: NLTK and spaCy.

## Setup

Before running the notebook, ensure you have the necessary libraries installed:

```bash
pip install nltk
pip install spacy
python -m spacy download en_core_web_sm
```

## Tokenization Techniques

### Word Tokenization with NLTK

Using NLTK's `word_tokenize` function to split a sample text into words:

```python
from nltk.tokenize import word_tokenize

sample_text = "this is a text ready to tokenize"
tokens = word_tokenize(sample_text)
print(sample_text, tokens)
```

### Tweet Tokenization with NLTK

Using NLTK's `TweetTokenizer` to handle special characters often found in tweets:

```python
from nltk.tokenize import TweetTokenizer

tweet_tokenizer = TweetTokenizer()
sample_text = "This is a tweet@jack#NLP"
tokens = tweet_tokenizer.tokenize(sample_text)
print(sample_text, tokens)
```

### Sentence Tokenization with NLTK

Using NLTK's `sent_tokenize` function to split a sample text into sentences:

```python
from nltk.tokenize import sent_tokenize

sample_text = "This is a sentence. This is another one!\nAnd this is the last one."
sentences = sent_tokenize(sample_text)
print(sample_text, sentences)
```

### Removing Stop Words with NLTK

Removing common stop words using NLTK's `stopwords` corpus:

```python
import nltk
from nltk.corpus import stopwords

nltk.download("stopwords")
stopwords_ = set(stopwords.words("english"))

sample_text = "this is a sample text"
tokens = sample_text.split()
clean_tokens = [t for t in tokens if not t in stopwords_]
clean_text = " ".join(clean_tokens)
print(sample_text, clean_text)
```

### Word Tokenization with spaCy

Using spaCy to tokenize a sample text into words:

```python
import spacy

nlp = spacy.load("en_core_web_sm")
sample_text = "this is a text ready to tokenize"
doc = nlp(sample_text)
tokens = [token.text for token in doc]
print(sample_text, tokens)
```

### Sentence Tokenization with spaCy

Using spaCy to tokenize a sample text into sentences:

```python
import spacy

nlp = spacy.load("en_core_web_sm")
sample_text = "This is a sentence. This is another one! \nAnd this is the last one."
doc = nlp(sample_text)
sentences = [sentence.text for sentence in doc.sents]
print(sample_text, sentences)
```

## Conclusion

This notebook provided an overview of different tokenization techniques using NLTK and spaCy. Tokenization is an essential step in text preprocessing for NLP tasks, and understanding various methods helps in choosing the right approach for different types of text data.
