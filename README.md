# Supervision vs. Demonstration-Based In-Context Learning for Multiword Expression Classification

This repository contains the data and code for the paper: 
**"Supervision vs. Demonstration-Based In-Context Learning for Multiword Expression Classification"**

## 📝TL;DR:
This research evaluates the performance of supervised BERTurk models versus LLMs (Llama 3.1, GPT-OSS, Qwen 2.5) in identifying Turkish idiomatic light verbs. We find that while zero-shot LLMs struggle with recall, master few-shot prompting yields robust overall performance and can match or exceed supervised baselines on the positive class.

## 📂Content

### 📑Datasets
This directory contains the LVC datasets used for training and evaluation.

* **Data Collection:** Potential light verbs were extracted from the following [Universal Dependencies](https://universaldependencies.org/tr/) Turkish treebanks:
    * Turkish-ATIS, Turkish-BOUN, Turkish-FrameNet, Turkish-GB, Turkish-IMST, Turkish-Kenet, Turkish-PUD, Turkish-Penn, Turkish-Tourism.
* **Refinement:** Extracted candidates were manually marked and human-verified. Incorrect entries were eliminated to produce the final dataset.
* **Evaluation Set:** A controlled test set ($N=147$) consisting of three balanced conditions ($n=49$ each):
    * **LVC:** Positive idiomatic/light-verb predicates.
    * **NLVC:** In-domain literal uses (non-idiomatic) sharing the same target verbs.
    * **Random:** Out-of-domain random negative controls.
* **Note:** The test set was constructed by manually writing specific examples for each category.

### 📊 Evaluation

The evaluation is structured into three main experiments based on different learning regimes:

### Task 1: Zero-Shot Prompting
Code for evaluating instruction-tuned LLMs (Llama 3.1-8B, GPT-OSS-20B, Qwen 2.5-14B) using only instructions.

### Task 2: One-Shot Prompting
Investigates how a single labeled example per target verb template affects model-specific biases and LVC detection.

### Task 3: Master Few-Shot Prompting
Evaluation under a master prompt providing multiple in-context demonstrations to improve calibration and robust performance.

### Task 4: Supervised Classification
Code for the supervised baseline using **BERTurk** (32k and 128k variants) with task-specific classifier heads trained on Turkish treebank data.

## 📄 Citation

If you use this work or the dataset, please cite our paper:
> Supervision vs. Demonstration-Based In-Context Learning for Multiword Expression Classification
