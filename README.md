# FRANK
refenrence: [SHG-VQA](https://github.com/aurooj/SHG-VQA)

### Build the conda environmnet
```
conda create --name STAR --file requiremets_conda.txt
conda activate STAR
pip install -r requirements_pip.txt
```
### Download data
Download ```STAR_train.json```, ```STAR_val.json```, ```STAR_test.json``` [here](https://bobbywu.com/STAR/)
```
./data
   |─ README.md
   |─ STAR_test.json
   |─ STAR_train.json
   └─ STAR_val.json
```
### Train
```
python3 STAR_run.py --train train --valid valid --llayers 5 --xlayers 2 --rlayers 5 \
--noCaps --crossAttnType cross --batchSize 32 --optim bert --lr 1e-5 --taskHGQA \
--fromScratch --LossHGPerFrame --epochs 100 --tqdm --output path/to/output/files \
--augmentType rand_aug --backbone slow_r50 --multiGPU
```
### Evaluation
```
python3 STAR_run.py--test test --llayers 5 --xlayers 2 --rlayers 5 \ 
--noCaps --LossHGPerFrame --crossAttnType cross --batchSize 8 --optim bert --lr 1e-5 --taskHGQA \
--fromScratch --indirectRef --epochs 100 --tqdm --output path/to/output/files \
--augmentType no_aug --backbone slow_r50 --load path/to/saved/model --multiGPU
```
