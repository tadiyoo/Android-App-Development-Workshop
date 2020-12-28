# Android-App-Development-Workshop
This repository contains all resources related to our Android App Development Workshop organized by Tadiyos , Paul and Simon collaboration with the CSE department @UESTC

# Requirements:
The following packages required to train both NTM and SAM:
1. tensorboard_logger
2. argcomplete
3. attrs
4. numpy
5. pytest
6. tqdm
7. pickle
8. argparse 
9. logging 

 They can be installed using:
 pip install package_name

# Neural Turing Machine (NTM):
For **NTM** both copy and repeat copy tasks are trained successfully and models saved under:
```
notebooks/copy
notebooks/repeat-copy
```
respectively.


For the above trained task I used the following command: 

## Copy Task:
```
copy those command
```

## Repeat Copy Task:
```
Repeat copy those command
```



# Self-attentive Associative Memory (SAM):
For **SAM** : the copy, Associative Recall and NFarthest tasks are trained  successfully using LSTM model plus partially trained using STM model and the models saved under:
```
saved_models folder
```
The log data for each task found in:
```
logs folder
``` 


To train those tasks on LSTM and STM:
## Copy Task:
#### Using LSTM baseline:
```  
python run_toys.py -task_json=./tasks/copy.json -model_name=lstm -mode=train
```
#### Using STM: 
```  
python run_toys.py -task_json=./tasks/copy.json -model_name=stm -mode=train
```

## Associative Recall: 
#### Using LSTM baseline:
``` 
python run_toys.py -task_json=./tasks/rar.json -model_name=lstm -mode=train
```
#### Using STM: 
```  
python run_toys.py -task_json=./tasks/rar.json -model_name=stm -mode=train
```

## NFarthest 
#### Using LSTM baseline:
``` 
python run_toys.py -task_json=./tasks/nfar.json -model_name=lstm -mode=train
```
#### Using STM: 
```  
python run_toys.py -task_json=./tasks/nfar.json -model_name=stm -mode=train
```

## Associative retrieval task
Generate Data  
```
cd datasets/number_arecall
python number_arecall.py
```
Train using STM:  
``` 
python run_nar.py -task_json=./tasks/nar.json -mode=train
```


