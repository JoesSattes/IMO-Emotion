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
# train a model on TweetEval dataset
sbatch submit_job_example.sh
```

```bash
# evaluate model on IMDB dataset
!python run_text_disentangled_classification.py --train_file dataset/sentiment/original_imdb/test.csv --validation_file dataset/sentiment/original_imdb/test.csv --model_name_or_path google-bert/bert-base-multilingual-cased  --output_dir checkpoints/out/ --model_class BertForTokenAttentionSparseCLSJoint_incremental --only_evaluation
```


