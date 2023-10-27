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

## How to cite
If you find our work useful for your research, please cite the papers using the following BibTex entry:

```
@inproceedings{10.1145/3593434.3593448,
author = {Doan, Thu T. H. and Nguyen, Phuong T. and Di Rocco, Juri and Di Ruscio, Davide},
title = {Too Long; Didn’t Read: Automatic Summarization of GitHub README.MD with Transformers},
year = {2023},
isbn = {9798400700446},
publisher = {Association for Computing Machinery},
address = {New York, NY, USA},
url = {https://doi.org/10.1145/3593434.3593448},
doi = {10.1145/3593434.3593448},
abstract = {The ability to allow developers to share their source code and collaborate on software projects has made GitHub a widely used open source platform. Each repository in GitHub is generally equipped with a README.MD file to exhibit an overview of the main functionalities. Nevertheless, while offering useful information, README.MD is usually lengthy, requiring time and effort to read and comprehend. Thus, besides README.MD, GitHub also allows its users to add a short description called “About,” giving a brief but informative summary about the repository. This enables visitors to quickly grasp the main content and decide whether to continue reading. Unfortunately, due to various reasons–not excluding laziness–oftentimes this field is left blank by developers. This paper proposes GitSum as a novel approach to the summarization of README.MD. GitSum is built on top of BART and T5, two cutting-edge deep learning techniques, learning from existing data to perform recommendations for repositories with a missing description. We test its performance using two datasets collected from GitHub. The evaluation shows that GitSum can generate relevant predictions, outperforming a well-established baseline.},
booktitle = {Proceedings of the 27th International Conference on Evaluation and Assessment in Software Engineering},
pages = {267–272},
numpages = {6},
keywords = {summarization, recommender systems, mining software repositories, README.MD, GitHub},
location = {Oulu, Finland},
series = {EASE '23}
}

```
