## 模型选择

Vision Transfromer    https://arxiv.org/abs/2010.11929

由于https://github.com/Jxhao99/DATA620004/tree/cifar100 中选择作为baseline的wide_resnet的

参数量约为35M，所以选择ViT-B_16(85.8M)，两者约在同一数量级上，可以作为对比。如果需要其他

的网络，可以参考https://github.com/jeonsworld/ViT-pytorch



## 文件下载

下载预训练权重ViT-B_16.npz放到 checkpoint 文件下

下载链接：

## 训练步骤

```bash
python3 train.py --name cifar10-100_500 --dataset cifar100 --model_type ViT-B_16 --pretrained_dir checkpoint/ViT-B_16.npz

###更多参数的设置可以参考train.py中

```



## CIFAR-100 训练结果

| network           | method   | epochs | size    | accuracy% |
| :---------------- | -------- | ------ | ------- | --------- |
| wide-resnet 28x10 | baseline | 200    | 32*32   | 81.34     |
| ViT-B_16          | baseline | 200    | 224*224 | 92.88     |
| ViT-B_16          | baseline | 200    | 32*32   | 62.19     |



## 参考

https://github.com/facebookresearch/mixup-cifar10.

https://github.com/szagoruyko/wide-residual-networks.

https://github.com/jeonsworld/ViT-pytorch
