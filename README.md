# NuAegis: Earnings Call Transcripts Summarization, Sentiment Analysis, and Conversational AI Integration

## Project Overview

This project leverages Natural Language Processing (NLP) techniques to analyze Earnings Call Transcripts (ECTs). It performs tasks such as summarization, sentiment-based summarization, and interactive Q&A through a chatbot. The final solution is implemented as an Android application, NuAegis, aimed at providing users with concise, actionable insights on financial reports.

## Table of Contents
1. [Objectives](#objectives)
2. [Dataset](#dataset)
3. [Methodology](#methodology)
   - [Data Collection](#data-collection)
   - [Summarization](#summarization)
   - [Sentiment-based Summarization](#sentiment-based-summarization)
   - [Conversational AI (Chatbot)](#conversational-ai-chatbot)
4. [Results](#results)
5. [User Interface](#user-interface)
6. [Installation](#installation)
7. [Usage](#usage)
8. [References](#references)

## Objectives

- Provide users with a summarized version of extensive earnings call transcripts.
- Generate sentiment-based summaries, offering both positive and negative viewpoints.
- Develop a chatbot for interactive financial Q&A, allowing personalized inquiries.

## Dataset

This project uses ECTs from the top 50 companies, scraped from AlphaSpread and organized by company, year, and quarter. Each transcript provides information about key financial metrics, enabling analysis across various time frames.

## Methodology

### Data Collection

- ECTs were scraped using BeautifulSoup and Requests libraries, cleaned, and stored as text files organized by company, year, and quarter.
- Standard preprocessing techniques (tokenization, lowercasing) were applied to the text.

### Summarization

- The BART transformer model was used for summarization, handling large transcripts by splitting them into manageable chunks.
- Generated summaries capture critical financial metrics, strategies, and market sentiments for each earnings call.

### Sentiment-based Summarization

1. **Sentiment Analysis**: Using a BiLSTM model with GloVe 100-d embeddings and multi-head attention mechanism, the model achieved 90% accuracy on the Financial Phrasebank dataset.
2. **Concise Summarization**: Leveraging the T5 model fine-tuned on the ECTSum dataset, the model generates sentiment-based summaries, classified as positive or negative with a context window of three sentences.

### Conversational AI (Chatbot)

- The chatbot module utilizes FinBERT embeddings for retrieving contextually relevant chunks of data based on user queries.
- Google Gemini model generates responses to user inquiries, enhanced with prompt engineering techniques for relevance and accuracy.

## Results

- **Summarization**: ROUGE-1 F1 Score of 0.2090 and ROUGE-L F1 Score of 0.1994.
- **Sentiment Analysis**: Test accuracy of 90% with BiLSTM and multi-head attention.
- **Concise Summarization**: ROUGE-1 score of 0.356, ROUGE-2 score of 0.237, ROUGE-L score of 0.326, with a high BERTScore F1 of 0.879.

## User Interface

The mobile application, NuAegis, includes separate pages for summarization, sentiment-based summaries, and chatbot interaction, allowing investors quick access to financial insights.

