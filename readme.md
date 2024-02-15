

# Dissecting learning and forgetting in language model finetuning

This repo provides code for finetuning language models on [pubmed](https://huggingface.co/datasets/pubmed) and evaluating models on corpus such as [pubmed_derived](https://huggingface.co/datasets/xiaozeroone/pubmed_derived).

The following commands are used to produce result in the [paper](https://openreview.net/forum?id=tmsqb6WpLz)

Training (on 8 A100 80GB GPUs)
```
accelerate launch --config_file config/deepspeed.yaml run.py --config-name train_full.yaml
```
Evaluation (on a single GPU)
```
python run.py --config-name eval_full.yaml
```

Hyperparameters, models and training/evaluation datasets are specified using config files in `config/`. Both full-finetuning and low-rank finetuning are supported.

## Citation
```
@inproceedings{
  zhang2024dissecting,
  title={Dissecting learning and forgetting in language model finetuning},
  author={Xiao Zhang and Ji Wu},
  booktitle={The Twelfth International Conference on Learning Representations},
  year={2024},
  url={https://openreview.net/forum?id=tmsqb6WpLz}
}
```
