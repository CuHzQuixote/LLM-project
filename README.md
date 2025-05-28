# LLM Project

## Project Task
This project fine-tunes a pre-trained T5-small transformer model on a news summarization task using the Multi-News dataset. The goal is to generate concise, high-quality summaries from multi-document news articles

## Dataset
We used a cleaned version of the [Multi-News dataset], consisting of news articles and their human-written summaries. For training, a sample of 500 document-summary pairs was used to ensure quick iteration in a Google Colab environment.

## Pre-trained Model
The model is based on t5-small, a lightweight variant of the T5 (Text-To-Text Transfer Transformer) model developed by Google. T5 treats every NLP task as a text-to-text task, including summarization.

## Performance Metrics
The fine-tuned model was evaluated using the ROUGE metric:

json
Copy
Edit
{
  "rouge1": 0.3165,
  "rouge2": 0.0955,
  "rougeL": 0.1927,
  "rougeLsum": 0.1930
}
These results show promising performance on a small sample size. ROUGE-1 and ROUGE-2 indicate the overlap of unigrams and bigrams with reference summaries.



## Hyperparameters
Key hyperparameters used during training:

Model: t5-small

Learning Rate: 5e-5

Batch Size: 4

Epochs: 3

Truncation length: 512 tokens for input, 128 for summaries

Training was accelerated using the 🤗 Accelerate library and only 500 samples were used to minimize runtime constraints.

