## Prerequisites
- Python 3.6
- PyTorch 0.4+
- GPU

## Getting started

### Dataset & Preparation
Download [CASIA-B Dataset](http://www.cbsr.ia.ac.cn/english/Gait%20Databases.asp)

#### Pretreatment
`pretreatment.py` uses the alignment method in
[this paper](https://ipsjcva.springeropen.com/articles/10.1186/s41074-018-0039-6).
Pretreatment your dataset by

### Train
Train a model by
```bash
python train.py
```
- `--cache` if set as TRUE all the training data will be loaded at once before the training start.
This will accelerate the training.

### Evaluation
Evaluate the trained model by
```bash
python test.py


# 554_final_project

