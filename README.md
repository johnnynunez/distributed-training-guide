# Distributed Training Guide

This guide aims at a comprehensive guide on best practices for distributed training, diagnosing errors, and fully utilize all resources available.

## Questions this guide answers:

#### How do I update a single gpu training/fine tuning script to run on multiple GPUs or multiple nodes?

*See chapters 2 & 3*

#### How do I diagnose hanging/errors that happen during training?

*See chapter 6*

#### My model/optimizer is too big for a single gpu - how do I train/fine tune it on my cluster?

*See chapter 5*

#### How do I schedule/launch training on a cluster?

*See chapter 4*

#### How do I scale my hyperparameters when increasing the number of workers?

*See chapters 94, 95, and 98*

---

Best practices for logging stdout/stderr and wandb are also included, as logging is vitally important in diagnosing/debugging training runs on a cluster.

## How to read

This guide is organized into sequential chapters, each with a `README.md` and a `train_llm.py` script in them. The readme will discuss the changes introduced in that chapter, and go into more details.

**Each of the training scripts is aimed at training a causal language model (i.e. gpt).**

## Set up

### Virtual Environment

```bash
python3 -m venv venv
source venv/bin/activate
python -m pip install -U pip
pip install -U setuptools wheel
pip install -r requirements.txt
```

### wandb

This tutorial uses `wandb` as an experiment tracker.

```bash
wandb login
```
