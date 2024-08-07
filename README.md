# IMO

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
python run_text_disentangled_classification.py --train_file dataset/sentiment/original_imdb/test.csv --validation_file dataset/sentiment/original_imdb/test.csv --model_name_or_path checkpoints/your_model  --output_dir checkpoints/out/ --model_class BartForTokenAttentionSparseCLSJoint_incremental --only_evaluation
```


