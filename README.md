## Faster-Rcnn：三种在预训练条件下的训练
---

## 目录
1. [性能情况 Performance](#性能情况)

2. [所需环境 Environment](#所需环境)

3. [文件下载 Download](#文件下载)

4. [训练步骤 How2train](#训练步骤)

   



## 性能情况


| 预训练情况   | 权重文件名称         | 训练数据集 | 测试数据集 | mAP   |
| ------------ | -------------------- | ---------- | ---------- | ----- |
| /            | /                    | VOC07+12   | VOC-Test07 | 60.07 |
| 基于ImageNet | imagenet_weights.pth | VOC07+12   | VOC-Test07 | 81.36 |
| 基于coco     | coco_weights.pth     | VOC07+12   | VOC-Test07 | 80.42 |



## 文件下载

预训练所需的imagenet_weights.pth  和 coco_weights.pth在百度云下载，下载后放到model_data文件夹。  
链接: https://pan.baidu.com/s/1S6wG8sEXBeoSec95NZxmlQ      
提取码: 8mgp    

VOC数据集下载地址如下，里面已经包括了训练集、测试集、验证集（与测试集一样），无需再次划分：  
链接: https://pan.baidu.com/s/1YuBbBKxm2FGgTU5OfaeC5A    
提取码: uack   



## 训练步骤

主要训练步骤参考

https://github.com/Jxhao99/DATA620004/tree/faster-rcnn

部分调整如下：

```bash
###对于(a),由于无需预训练权重
		
		所以python train.py --pretrained False
		
###对于(b),采用imagenet预训练权重，权重名称imagenet_weights
		
		所以python train.py --pre_data imagenet(默认可省略)
		
###对于(c),采用coco训练的Mask R-CNN的backbone

		所以python train.py --pre_data coco

```



tensorboard可视化以后的结果默认在runs文件下

## Reference

https://github.com/chenyuntc/simple-faster-rcnn-pytorch  
https://github.com/eriklindernoren/PyTorch-YOLOv3  
https://github.com/BobLiu20/YOLOv3_PyTorch  
