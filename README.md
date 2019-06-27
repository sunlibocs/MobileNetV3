# Paper
- [Searching for MobileNetV3 paper](https://arxiv.org/abs/1905.02244)
- Author: Andrew Howard(Google Research), Mark Sandler(Google Research, Grace Chu(Google Research), Liang-Chieh Chen(Google Research), Bo Chen(Google Research), Mingxing Tan(Google Brain), Weijun Wang(Google Research), Yukun Zhu(Google Research), Ruoming Pang(Google Brain), Vijay Vasudevan(Google Brain), Quoc V. Le(Google Brain), Hartwig Adam(Google Research)

## Summary

- The model.py comes from https://github.com/xiaolai-sqlai/mobilenetv3 

- We test both small and large mobileNetv3 on CIFAR-100 using our trained model, train code and test code. Our trained mode can be found from ./checkpoint

- For the experiment on imageNet, we didn't train our own model, and we just use the contained pretrained model from the above link. We found that there is a accuracy difference between our result and their result. We got an acc1 of 65.07%, while they obatained 69.037%. This difference was also issued by someone else - https://github.com/xiaolai-sqlai/mobilenetv3/issues/18


## Experiments
- For CIFAR-100 and imageNet data, we experimented with resize (224, 224).

| Datasets | Model | Accuracy | Epoch | Training Time | Parameters |
| :---: | :---: | :---: | :---: | :---: | :---: |
| CIFAR-100 | MobileNetV3-LARGE | 69.92% | 34 | 3h 58min | 2.8M|
| CIFAR-100 | MobileNetV3-SMALL | 68.67% | 35 | 1h 25min | 1.35M|

- For imageNet, we didn't train our own model. We just report the results from original paper, the pretrained model provider and ourselves(use the same pretrained model). 

| Datasets | Model | Accuracy | Parameters |
| :---: | :---: | :---: | :---: |
| IMAGENET | MobileNetV3-LARGE(paper)| 75.2% | 5.4M | 
| IMAGENET | MobileNetV3-SMALL(paper)| 67.4%| 2.9M | 
| IMAGENET | MobileNetV3-SMALL(pretrained model provider)| 69.037% | 2.52M | 
| IMAGENET | MobileNetV3-SMALL(Ours) | 65.07% | 2.52M | 
## Environment
- torch==1.1.0
- 32G Mem + 1GPU(K80)
