# IMO-Emotion version
This repository revised and reproduced the version of the IMO paper, which focuses on sentiment analysis tasks.

## Table of Contents
- [Setup](#installation)
- [Usage](#usage)

## Setup
Install Dependency:
```
pip install datasets transformers evaluate
```

## Usage
### Training and Evaluate Models
Run the following command to start the training process:
```bash
# train on IMDB
python run_text_disentangled_classification.py --train_file dataset/sentiment/original_imdb/tc_train.csv --validation_file dataset/sentiment/original_imdb/tc_valid.csv --model_name_or_path google-bert/bert-base-multilingual-cased  --output_dir checkpoints/mbart_imdb --model_class BertForTokenAttentionSparseCLSJoint_incremental --num_train_epochs 1 --hidden_state_layer 8 --seed 415

# train on Tweet
python run_text_disentangled_classification.py --train_file dataset/sentiment/TweetEval_sentiment/train/tc_train.csv --validation_file dataset/sentiment/TweetEval_sentiment/valid/tc_valid.csv --model_name_or_path google-bert/bert-base-multilingual-cased  --output_dir checkpoints/mbart_tweet --model_class BertForTokenAttentionSparseCLSJoint_incremental --num_train_epochs 5 --hidden_state_layer 8 --seed 415
```

```bash
# evaluate model on IMDB dataset
python run_text_disentangled_classification.py --train_file dataset/sentiment/original_imdb/test.csv --validation_file dataset/sentiment/original_imdb/test.csv --model_name_or_path google-bert/bert-base-multilingual-cased  --output_dir checkpoints/out/ --model_class BertForTokenAttentionSparseCLSJoint_incremental --hidden_state_layer 8 --prediction_result_file mbart_preds.csv --only_evaluation
```


