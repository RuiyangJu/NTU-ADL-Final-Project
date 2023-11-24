# 2023 NTU ADL Final Project - Group 8
## Environment
* Linux (Ubuntu)
* Python >= 3.6 (Pytorch)
* NVIDIA GPU + CUDA CuDNN
```
  cd 23-ADL-Final-Project
  pip install -r requirements.txt
```

## Download
Use gdown to download dataset from Google Drive:
```
  bash download.sh
```

## Preprocess
Before you run the following steps, make sure `cd 23-ADL-Final-Project`.
```
  python preprocess/image_to_256.py
```
```
  python preprocess/image_to_512.py
```

## Enhancement
```
  python enhancement.py --gpu 0 --epochs 10 --base_model_name efficientnet-b0 --batch_size 16
```

## Local Prediciton Preparation
```
  python to_local_prediction.py --gpu 0 --original_dir data/Trainset/image/ --image_train_dir data/Trainset_256/image --mask_train_dir data/Trainset_256/mask --image_test_dir data/Testset/image --mask_test_dir data/Testset/mask --base_model_name efficientnet-b0
```
