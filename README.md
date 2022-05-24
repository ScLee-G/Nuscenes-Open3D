# Nuscenes dataset visualization with Open3D
## Download Nuscenes dataset
Users can download the dataset from [nuscenes](https://www.nuscenes.org/nuscenes).
The download command is: 
```
wget /path/to/datase/on/uscenes.org
```
## Preprocess dataset
The raw schema of dataset after downloading should be:
```bash
├── maps
├── samples
├── sweeps
└── v1.0-mini
```
Open3D has provided a preprocess function in [Open3D-ML/scripts](https://github.com/isl-org/Open3D-ML/tree/master/scripts). We can just use this preprocess function.

Preprocess command is (here we use v1.0-mini dataset):
```
python preprocess_nuscenes.py --dataset_path /path/to/dataset --version v1.0-mini
```
After preprocessing, there will be two .pkl files, containing list information of sweeps.
The schema after preprocessing should be:
```bash
├── infos_train.pkl
├── infos_val.pkl
├── maps
├── samples
├── sweeps
└── v1.0-mini
```
## Visualization with Open3D


