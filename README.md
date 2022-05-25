# Nuscenes visualization based on Open3D
This is a demo of visualizing nuscenes based on [Open3D](https://github.com/isl-org/Open3D-ML) library, including lidar point clouds and camera images.
## Download Open3D library
The latest version of Open3D is 0.15.
We can use the following command to install the library.
```bash
pip install open3d==0.15.2
```
Note: Please pay attention to the issue: [pip can't find 0.15.1](https://github.com/isl-org/Open3D/issues/4796)
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
Open3D has released Open3D 0.15.0 version. In Open3D 0.15.0, authors not only released Open3D-dedicated Command Line Interface (CLI) for visualization and running Python examples, but also added support for Images in Dataset Visualizer.

```bash
python visualize.py nuscenes /path/to/nuscenes/dataset
```
The following picture and video show the visualization of nuscenes with Open3D. 
![Visualiztaion screenshot](https://github.com/ShuchangLi/Nuscenes-visualization-Open3D/blob/main/img_folder/screenshot.png)
[Video demo](https://github.com/ShuchangLi/Nuscenes-visualization-Open3D/blob/main/img_folder/nuscenes_demo.mp4)

