# Enviroment Setup Note 
Sience the `Pillow` lib needed for `torchvision` now having a [issue](https://github.com/pytorch/vision/issues/1712), causing the ERROE `ImportError: cannot import name 'PILLOW_VERSION' from 'PIL' `, please DON'T use Pillow lib version no less than `7.0`.    

> 2020-01-08

# Train CIFAR10 with PyTorch

I'm playing with [PyTorch](http://pytorch.org/) on the CIFAR10 dataset.

## Prerequisites
- Python 3.6+
- PyTorch 1.0+

## Accuracy
| Model             | Acc.        |
| ----------------- | ----------- |
| [VGG16](https://arxiv.org/abs/1409.1556)              | 92.64%      |
| [ResNet18](https://arxiv.org/abs/1512.03385)          | 93.02%      |
| [ResNet50](https://arxiv.org/abs/1512.03385)          | 93.62%      |
| [ResNet101](https://arxiv.org/abs/1512.03385)         | 93.75%      |
| [MobileNetV2](https://arxiv.org/abs/1801.04381)       | 94.43%      |
| [ResNeXt29(32x4d)](https://arxiv.org/abs/1611.05431)  | 94.73%      |
| [ResNeXt29(2x64d)](https://arxiv.org/abs/1611.05431)  | 94.82%      |
| [DenseNet121](https://arxiv.org/abs/1608.06993)       | 95.04%      |
| [PreActResNet18](https://arxiv.org/abs/1603.05027)    | 95.11%      |
| [DPN92](https://arxiv.org/abs/1707.01629)             | 95.16%      |

## Learning rate adjustment
Using ` torch.optim.lr_scheduler.MultiStepLR`

Multi step learning rate decay

lr = 0.1     if epoch < 150

lr = 0.01    if 150 <= epoch < 250

lr = 0.001   if epoch >= 250



Resume the training with `python main.py --resume --lr=0.01`
