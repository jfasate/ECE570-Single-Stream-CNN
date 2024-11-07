# CNNs for Multi-Source Remote Sensing Data Fusion

## Environment Setup
Before starting the code implementation, please set up a `conda` environment for package management. This ensures all dependencies are isolated and easily manageable.

1. **Install Conda**:
   Make sure you have [Anaconda](https://www.anaconda.com/products/distribution) or [Miniconda](https://docs.conda.io/en/latest/miniconda.html) installed.

2. **Create and Activate Conda Environment**:
   ```bash
   conda create -n cnn_env
   conda activate cnn_env

## Requirement
- python3
- pytorch
- CUDA
- cuDNN
- torchvision
- gdal
- sklearn (scipy, numpy)

## Data
Data files are available at [this Google Drive site](https://drive.google.com/drive/folders/1urY6Pjba3mStDcRphIfkNf50295aW2o2?usp=sharing), which can be directly used in this code. Please note that we used channel-wise normalization AFTER loading these files, and this step is already implemented in our code. 

Below are links to the original data sets:

[[Houston2018]](https://ieee-dataport.org/open-access/2018-ieee-grss-data-fusion-challenge-%E2%80%93-fusion-multispectral-lidar-and-hyperspectral-data) &nbsp;
[[Berlin]](https://github.com/danfenghong/ISPRS_S2FL) &nbsp;
[[MUUFL]](https://github.com/GatorSense/MUUFLGulfport/tree/master/MUUFLGulfportSceneLabels) &nbsp;

## Run
To load the training data, modify ```common.py```. Arguments are automatically loaded to ```main.py```

1) Open ```common.py```
2) Manually create a folder named train_model in your project directory to store model checkpoints during training.
3) In the Config class of common.py, set ```save_ckpt_dir = 'path/to/train_model'```
4) In the Config class of common.py, set ```result_out_dir = 'path/to/results'```
5) In the Config class of common.py, set ```data_dir = 'path/to/data'```

- Simply run 
```
python3 main.py
```

## Results

| Dataset | OA (%) | Kappa |
| --- | ----------- | ----- |
| Houston2018 | 63.74 | 0.62 |
| Berlin | 68.21 | 0.54 |
| MUUFL | 86.44 | 0.83 |

## Citation

If you find our work helpful, please kindly cite: 
```
@ARTICLE{9761218,
  author={Yang, Yi and Zhu, Daoye and Qu, Tengteng and Wang, Qiangyu and Ren, Fuhu and Cheng, Chengqi},
  journal={IEEE Transactions on Geoscience and Remote Sensing}, 
  title={Single-Stream CNN With Learnable Architecture for Multisource Remote Sensing Data}, 
  year={2022},
  volume={60},
  number={},
  pages={1-18},
  doi={10.1109/TGRS.2022.3169163}}
```
