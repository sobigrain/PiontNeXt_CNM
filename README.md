# PointNeXt_CNM
---

## Installation
We provide a simple bash file to install the environment:

```
git clone --recurse-submodules git@github.com:guochengqian/PointNeXt.git
cd PointNeXt
source update.sh
source install.sh
```
Cuda-11.3 is required. Modify the `install.sh` if a different cuda version is used. See [Install](docs/index.md) for detail. 

## Usage 
Check our [online documentation](https://guochengqian.github.io/PointNeXt/) for detailed instructions. 

A short instruction: all experiments follow the simple rule to train and test: 

```
CUDA_VISIBLE_DEVICES=$GPUs python examples/$task_folder/main.py --cfg $cfg $kwargs
```
- $GPUs is the list of GPUs to use, for most experiments (ScanObjectNN, ModelNet40, S3DIS), we only use 1 A100 (GPUs=0)
- $task_folder is the folder name of the experiment. For example, for s3dis segmentation, $task_folder=s3dis
- $cfg is the path to cfg, for example, s3dis segmentation, $cfg=cfgs/s3dis/pointnext-s.yaml
- $kwargs are the other keyword arguments to use. For example, testing in S3DIS area 5, $kwargs should be `mode=test, --pretrained_path $pretrained_path`. 

---

### Acknowledgment
This library is inspired by [PyTorch-image-models](https://github.com/rwightman/pytorch-image-models) and [mmcv](https://github.com/open-mmlab/mmcv). 



### Citation
If you find PointNeXt or the OpenPoints codebase useful, please cite:
```tex
@InProceedings{qian2022pointnext,
  title   = {PointNeXt: Revisiting PointNet++ with Improved Training and Scaling Strategies},
  author  = {Qian, Guocheng and Li, Yuchen and Peng, Houwen and Mai, Jinjie and Hammoud, Hasan and Elhoseiny, Mohamed and Ghanem, Bernard},
  booktitle=Advances in Neural Information Processing Systems (NeurIPS),
  year    = {2022},
}
```
