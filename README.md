git clone git@github.com:HankStat/JH_seniorproj.git  
python3.7 -m venv ilf  
source ilf/bin/activate  
pip install -r requirements.txt  
pip uninstall transformers  
pip install transformers  
pip install --upgrade accelerate  
wget -P checkpoints https://storage.googleapis.com/sfr-codegen-research/checkpoints/codegen-350M-mono.tar.gz && tar -xvf checkpoints/codegen-350M-mono.tar.gz -C checkpoints/  
source ilf_pipeline.sh -d $(pwd) -n test  
