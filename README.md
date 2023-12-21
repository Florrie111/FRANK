### Build the conda environmnet
```
conda create --name STAR --file requiremets_conda.txt
conda activate STAR
pip install -r requirements_pip.txt
```
### Download data
Download train.json, val.json, test.json [here](https://bobbywu.com/STAR/)
```
./data
   |─ README.md
   |─ STAR_test.json
   |─ STAR_train.json
   └─ STAR_val.json
```
