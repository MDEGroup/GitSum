# GitSum guidelines

## Pre-requisites:
Installing neccessary packages:
```shell script
pip install datasets transformers rouge-score nltk
```

## Fine-tuning pre-trained models
Run the script in `src/fine-tune-model.py` to fine-tune pre-trained BART model with the default configuration in `src/args_bart.json`

Change reference variable `json_file` in the script to `src/args_t5.json` in order to fine-tune pre-trained T5 model for this task

Running  the script `src/fine-tune-model.py` also perform evaluation on the test dataset. All output is saved in `models` directory as default. Every settings can be changed by manipulating the `json` configuration file, regarded as `src/args_t5.json` or `src/args_bart.json`
