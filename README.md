##  Deep Constrained Dominant Sets for Person Re-Identification (DCDS)
Pytorch Implementation for our ICCV2019 work called Deep Constrained Dominant Sets for Person Re-Identification
This implementation is based on Oper Reid and kpm_rw_person_reid

### Requirements 
* python 2.7 
* PyTorch (we run the code under version 0.3.0)
* metric-learn 0.3.0
* torchvision 0.2.1

```shell 
- cd DCDS
- install setup.py
```


For single dataset (SD) setup we use [Market1501](https://drive.google.com/file/d/0B8-rUzbwVRk0c054eEozWG9COHM/view), [CUHK03](//docs.google.com/spreadsheet/viewform?usp=drive_web&formkey=dHRkMkFVSUFvbTJIRkRDLWRwZWpONnc6MA#gid=0), and [DukeMTMC](https://drive.google.com/uc?id=0B0VOCNYh8HeRdnBPa2ZWaVBYSVk) datasets.
### Download and extract these datasets and do,
```shell 
cd examples/
mkdir data
cd data/
mkdir market1501
cd market1501
mkdir raw/
mv dir_of_market1501_zip raw/
```
Repeate this for CUHK03 and Dukemtmc.



## Example

### Training
```
-d market1501 -b 64 -a resnet101 --features 2048 --lr 0.0001 --ss 10 --epochs 100 --dropout 0 --weight-decay 0 --logs-dir examples/logs/market1501-final-model
```
```
-d dukemtmc -b 64 -a resnet101 --features 2048 --lr 0.0001 --ss 10 --epochs 100 --dropout 0 --weight-decay 0 --logs-dir examples/logs/dukemtmc-final-model
```

- Same for CUHK03

### Testing
Download our models
* Market1501
* DukeMTMC
* CUHK03
```
-d market1501 -b 64 -a resnet101 --features 2048 --evaluate --evaluate-from examples/logs/market1501-final-model/model_best.pth.tar

-d dukemtmc -b 64 -a resnet101 --features 2048 --evaluate --evaluate-from examples/logs/dukemtmc-final-model/model_best.pth.pth.tar
```



