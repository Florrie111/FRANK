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
