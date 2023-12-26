# FRANK
refenrence: [SHG-VQA](https://github.com/aurooj/SHG-VQA)

### Build the environmnet
```
git clone https://github.com/Florrie111/FRANK.git
cd FRANK
conda create --name STAR --file requirements_conda.txt
conda activate STAR
pip install -r requirements_pip.txt
```
Please replace the TODO parts in ```src/task/star_data.py``` with your directories.

### Download data
Download ```STAR_train.json```, ```STAR_val.json```, ```STAR_test.json``` [here](https://bobbywu.com/STAR/)
```
./data
   |─ README.md
   |─ STAR_test.json
   |─ STAR_train.json
   └─ STAR_val.json
```
Follow the instructions [here](https://github.com/JingweiJ/ActionGenome/tree/master) to generate the frames (~58.9 GB).
```
./FRANK
   |─ annotations/
   |─ data/
   |─ frames/
   |   .
   |   .
   |   .
   └─ STAR_run.py
```
### Train
```
python3 STAR_run.py --train train --valid valid --llayers 5 --xlayers 2 --rlayers 5 --noCaps --crossAttnType cross --batchSize 32 --optim bert --lr 1e-5 --taskHGQA --fromScratch --LossHGPerFrame --epochs 100 --tqdm --output results/train  --augmentType rand_aug --backbone slow_r50 --multiGPU
```
### Evaluation
```
python3 STAR_run.py --test test --llayers 5 --xlayers 2 --rlayers 5 --noCaps --LossHGPerFrame --crossAttnType cross --batchSize 8 --optim bert --lr 1e-5 --taskHGQA --fromScratch --indirectRef --epochs 100 --tqdm --output results/eval --augmentType no_aug --backbone slow_r50 --load results/train/BEST --multiGPU
```
