# Thai News Classification Model
This project involves training a text classification model on a Thai news dataset from Prachatai, a well-known Thai news source, to perform various Natural Language Processing (NLP) tasks, including language modeling and classification. The model, built using the fastai library and pythainlp, is fine-tuned to understand and classify news articles in the Thai language effectively. Here’s an overview of the workflow and key components of the project:

## Project Workflow
1. Data Source:
- The dataset used in this project consists of news articles from Prachatai, providing a comprehensive source of Thai news content suitable for text classification tasks.
2. Data Preparation:
- Load training, validation, and test datasets (train_df.csv, valid_df.csv, test_df.csv) from preprocessed Thai news articles.
- Concatenate the datasets for language model training and store the combined data for efficient access.
3. Vocabulary and Tokenization:
- Utilize pre-trained Thai vocabulary (THWIKI_LSTM) and custom tokenization tailored for Thai text, leveraging pythainlp and fastai.
- Apply tokenization and numericalization with a vocab size limit of 60,000 to process the text data for model training.
4. Language Model Training:
- Construct a language model data object using TextList from fastai.
- Train a ULMFiT (Universal Language Model Fine-tuning) model using the Thai language, initialized with a pre-trained model on Thai Wikipedia (THWIKI_LSTM).
- Implement both frozen and unfrozen training phases to adapt the model to the specific characteristics of the Thai news dataset.
5. Text Classification Model:
- Prepare a separate data object for text classification, with the processed vocabulary from the language model phase.
- Fine-tune the language model as a classifier to categorize news articles based on their content, employing a multi-layered AWD-LSTM architecture.
- Implement staged training by gradually unfreezing model layers for optimized performance on the validation set.
6. Testing and Evaluation:
- Run the model on the test set to generate predictions, saving the output probabilities for further analysis or performance benchmarking.

## Usage
To train and evaluate the model, follow these steps:
1. Prepare your datasets and place them in the specified file paths.
2. Load the pre-trained Thai vocabulary and tokenization configurations.
3. Run the script for language model training, followed by classification model training.
4. Evaluate the model on the test set and review the predictions.

This model serves as a valuable resource for applications involving Thai text classification, providing a fine-tuned model tailored for Thai news articles and ready for integration into various NLP pipelines.
