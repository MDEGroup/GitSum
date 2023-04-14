# GitSum guidelines
This repository contains the source code implementation of `GitSum` and the datasets
used to replicate the experimental results of our paper:

*Too long; didn’t read: Automatic summarization of GitHub
README.MD with Transformers*

Thu T. H. Doan,<sup>(1)</sup> Phuong T. Nguyen, Juri Di Rocco, Davide Di Ruscio<sup>(2)</sup>

<sup>(1)</sup> VNU University of Engineering & Technology, Hanoi, Vietnam

<sup>(2)</sup> Università degli Studi dell'Aquila, Italy

The paper has been accepted to the Vision and Emerging Results Papers track of the International Conference on Evaluation and Assessment in Software Engineering (EASE 2023).

## Introduction
`GitSum` is a novel approach to the summarization of README.MD, 
automatically filling the blank “About” field for repositories. 
It is built on top of BART and T5, two cutting-edge deep learning techniques,
learning from existing data to perform recommendations 
for repositories with a missing description. 
We test its performance using two datasets collected from GitHub. 
The evaluation shows that GitSum can generate highly relevant predictions, 
outperforming a well-established baseline.

## Pre-requisites:
Installing neccessary packages:
```shell script
pip install datasets transformers rouge-score nltk
```

## Fine-tuning pre-trained models
Run the script in `src/fine-tune-model.py` to fine-tune pre-trained BART model with the default configuration in `src/args_bart.json`

Change reference variable `json_file` in the script to `src/args_t5.json` in order to fine-tune pre-trained T5 model for this task

Running  the script `src/fine-tune-model.py` also perform evaluation on the test dataset. All output is saved in `models` directory as default. Every settings can be changed by manipulating the `json` configuration file, regarded as `src/args_t5.json` or `src/args_bart.json`
