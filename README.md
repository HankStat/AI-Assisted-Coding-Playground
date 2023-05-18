## Reference
https://github.com/nyu-mll/ILF-for-code-generation

## Requirements
Ubuntu 22.04  
Python 3.7
## Installation
create virtual environment ilf & activate  

```
git clone git@github.com:HankStat/JH_seniorproj.git  
python3.7 -m venv ilf  
source ilf/bin/activate
```

install all dependencies    
download codgen-350M-mono  
make sure that CUDA is compatible with PyTorch
```
pip install -r requirements.txt  
pip uninstall transformers  
pip install transformers  
pip install --upgrade accelerate  
wget -P checkpoints https://storage.googleapis.com/sfr-codegen-research/checkpoints/codegen-350M-mono.tar.gz && tar -xvf checkpoints/codegen-350M-mono.tar.gz -C checkpoints/  
```

## Run the pipeline  
```
source ilf_pipeline.sh -d $(pwd) -n <EXPERIMENT_NAME>
```
with <EXPERIMENT_NAME> replaced with the name of the subdirectory that you wish to store results in.

## sh file
  
|Python file|   Description   |  
|--------------------------|----------------------------------|
|preprocess_feedback_spreadsheet.py|Preprocess the data|
|finetune_refinement_model.py|Fine-tune a model to generate refinements|
|generate_refinements_codegen_finetuned.py|Generate refinements|
|eval_mbpp.py|Evaluate refinements generated for training data|
|create_finetuning_data_from_refinements.py|create finetuning data from refinements|
|finetune.py|Fine-tune two separate models|
|generate_code_for_mbpp.py|Evaluate models on testing data|
|eval_mbpp.py|evaluate final generations|