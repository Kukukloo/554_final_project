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
```
python pretreatment.py --input_path='root_path_of_raw_dataset' --output_path='root_path_for_output'
```
- `--input_path` **(NECESSARY)** Root path of raw dataset.
- `--output_path` **(NECESSARY)** Root path for output.
- `--log_file` Log file path. #Default: './pretreatment.log'
- `--log` If set as True, all logs will be saved. 
Otherwise, only warnings and errors will be saved. #Default: False
- `--worker_num` How many subprocesses to use for data pretreatment. Default: 1

### Configuration 

In `config.py`, you might want to change the following settings:
- `dataset_path` **(NECESSARY)** root path of the dataset 
(for the above example, it is "gaitdata")
- `WORK_PATH` path to save/load checkpoints
- `CUDA_VISIBLE_DEVICES` indices of GPUs

### Train
Train a model by
```bash
python train.py
```
- `--cache` if set as TRUE all the training data will be loaded at once before the training start.
This will accelerate the training.
**Note that** if this arg is set as FALSE, samples will NOT be kept in the memory
even they have been used in the former iterations. #Default: TRUE

### Evaluation
Evaluate the trained model by
```bash
python test.py
```
- `--iter` iteration of the checkpoint to load. #Default: 80000
- `--batch_size` batch size of the parallel test. #Default: 1
- `--cache` if set as TRUE all the test data will be loaded at once before the transforming start.
This might accelerate the testing. #Default: FALSE

It will output Rank@1 of all three walking conditions. 
Note that the test is **parallelizable**. 
To conduct a faster evaluation, you could use `--batch_size` to change the batch size for test.


## Citation
Please cite these papers in your publications if it helps your research:
```
@ARTICLE{chao2019gaitset,
  author={Chao, Hanqing and Wang, Kun and He, Yiwei and Zhang, Junping and Feng, Jianfeng},
  journal={IEEE Transactions on Pattern Analysis and Machine Intelligence}, 
  title={GaitSet: Cross-view Gait Recognition through Utilizing Gait as a Deep Set}, 
  year={2021},
  pages={1-1},
  doi={10.1109/TPAMI.2021.3057879}}
```
Link to paper:
- [GaitSet: Cross-view Gait Recognition through Utilizing Gait as a Deep Set](https://ieeexplore.ieee.org/document/9351667)


# 554_final_project
