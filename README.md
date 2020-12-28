# Android-App-Development-Workshop
This repository contains all resources related to our Android App Development Workshop organized by Tadiyos , Paul and Simon collaboration with the CSE department @UESTC

# Requirements:
The following package required to train both NTM and SAM:
1. tensorboard_logger
2. argcomplete
3. attrs
4. numpy
5. pytest
6. tqdm
7. pickle
8. argparse 
9. logging 
10. args

 They can be installed using:
 pip install package_name

# Neural Turing Machine (NTM):
For **NTM** both copy and repeat copy tasks are trained successfully and models saved under:
```
notebooks/copy
notebooks/repeat-copy
```
respectively.


## Usage

```
Execute: python train.py [-h] [--seed SEED] [--task {copy,repeat-copy}] [-p PARAM]
                [--checkpoint-interval CHECKPOINT_INTERVAL]
                [--checkpoint-path CHECKPOINT_PATH]
                [--report-interval REPORT_INTERVAL]

optional arguments:
  -h, --help            show this help message and exit
  --seed SEED           Seed value for RNGs
  --task {copy,repeat-copy}
                        Choose the task to train (default: copy)
  -p PARAM, --param PARAM
                        Override model params. Example: "-pbatch_size=4
                        -pnum_heads=2"
  --checkpoint-interval CHECKPOINT_INTERVAL
                        Checkpoint interval (default: 1000). Use 0 to disable
                        checkpointing
  --checkpoint-path CHECKPOINT_PATH
                        Path for saving checkpoint data (default: './')
  --report-interval REPORT_INTERVAL
                        Reporting interval
```
For the above trained task I used the following command: 

## Copy Task:


## Repeat Copy Task:




# Self-attentive Associative Memory (SAM):
For **SAM** : the copy, Associative Recall and NFarthest tasks are trained  successfully using LSTM model plus partially trained using STM model and the models saved under:
```
saved_models folder
```
The log data for each task found in:
```
logs folder
``` 


# To train those tasks on LSTM and STM:
## Copy Task:
#### LSTM baseline:
```  
python run_toys.py -task_json=./tasks/copy.json -model_name=lstm -mode=train
```
#### STM: 
```  
python run_toys.py -task_json=./tasks/copy.json -model_name=stm -mode=train
```

## Associative Recall: 
#### LSTM baseline:
``` 
python run_toys.py -task_json=./tasks/rar.json -model_name=lstm -mode=train
```
#### STM: 
```  
python run_toys.py -task_json=./tasks/rar.json -model_name=stm -mode=train
```

## NFarthest 
#### LSTM baseline:
``` 
python run_toys.py -task_json=./tasks/nfar.json -model_name=lstm -mode=train
```
#### STM: 
```  
python run_toys.py -task_json=./tasks/nfar.json -model_name=stm -mode=train
```

# Associative retrieval task
generate data  
```
cd datasets/number_arecall
python number_arecall.py
```
STM training  
``` 
python run_nar.py -task_json=./tasks/nar.json -mode=train
```

