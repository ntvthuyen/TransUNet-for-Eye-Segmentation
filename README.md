# TransUNet for Eye Segmentation


This repo holds code for Eye Segmentation task using TransUnet [TransUNet: Transformers Make Strong Encoders for Medical Image Segmentation](https://arxiv.org/pdf/2102.04306.pdf)


## Usage

### 1. Download Google pre-trained ViT models
* [Get models in this link](https://console.cloud.google.com/storage/vit_models/): R50-ViT-B_16, ViT-B_16, ViT-L_16...
```bash
wget https://storage.googleapis.com/vit_models/imagenet21k/{MODEL_NAME}.npz &&
mkdir ../model/vit_checkpoint/imagenet21k &&
mv {MODEL_NAME}.npz ../model/vit_checkpoint/imagenet21k/{MODEL_NAME}.npz
```

### 2. Prepare data

The model uses OpenEDS dataset.

[Link to OpenEDS dataset](https://www.kaggle.com/datasets/soumicksarker/openeds-dataset)

### 3. Environment

Please prepare an environment with python=3.9, and then use the command "pip install -r requirements.txt" for the dependencies.

### 4. Train/Test

- Run the train script on OpenEDS dataset.

```bash
CUDA_VISIBLE_DEVICES=0 python train.py --dataset OpenEDS --vit_name R50-ViT-B_16
```

- Run the test script on OpenEDS dataset

```bash
python test.py --dataset OpenEDS --vit_name R50-ViT-B_16
```
### 5. Inference 

- import class from infer.py

## Reference
* [Google ViT](https://github.com/google-research/vision_transformer)
* [ViT-pytorch](https://github.com/jeonsworld/ViT-pytorch)
* [segmentation_models.pytorch](https://github.com/qubvel/segmentation_models.pytorch)
## Citations


```bibtex
@article{chen2021transunet,
  title={TransUNet: Transformers Make Strong Encoders for Medical Image Segmentation},
  author={Chen, Jieneng and Lu, Yongyi and Yu, Qihang and Luo, Xiangde and Adeli, Ehsan and Wang, Yan and Lu, Le and Yuille, Alan L., and Zhou, Yuyin},
  journal={arXiv preprint arXiv:2102.04306},
  year={2021}
}
```
