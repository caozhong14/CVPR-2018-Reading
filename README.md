# CVPR-2018-Reading

## [Unsupervised Person Image Synthesis in Arbitrary Poses][1]

#Image Synthesis
CVPR 2018 Spotlight 论文，ReID + GAN 换 pose。

本文用了较多的篇幅讲 loss function，pose 的提取用的是 OpenPose 这个库。 
其 loss 分为三部分： 

1. Image Adversarial Loss：即传统 GAN 的 loss；
2. Pose Loss：pose 差异，生成后的图片再用 OpenPose 提取 pose 信息做差值；
3. Identity Loss：此为关键，又分为两部分，分别是 content 和 style loss，其中 content 用于保证生成图和原图在某 pretrain model 生成的 feature map 一致， style 则是利用 Gram matrix 生成某种 feature map，然后作比对。


[笔记链接][2]


## [Person Transfer GAN to Bridge Domain Gap for Person Re-Identification][3]

#Person ReID

CVPR 2018 RE-ID Spotlight 一篇，这篇文章主要 contribution 有以下两点： 

1. 提出了一个新的更大的数据集，更为细致：考虑到了视角，光照等更为细致的因素，具体参数可以直接看文章；
2. 多个数据集间的差异，即 domain-gap，通过 GAN 来生成和模仿，类似文章：Camera Style Adaptation for Person Re-identification，个人认为创意是有的，可以作为 data augmentation 的一个方法，但实现难度上并没有很大。

[代码链接][4]
[数据集链接][5]
[笔记链接][6]


## [Disentangled Person Image Generation][7]

#Image Generation

在 NIPS 2017 上，该团队已经为我们贡献了 Pose Guided Person Image Generation 这篇非常棒的文章，在 CVPR 2018 中，他们推出的更新的这篇文章不仅仅解决了换 pose 问题，还实现了”随心所欲“的换装换 pose，入选今年的 Spotlight。 

在这里提到的前一篇文章可复现度很高，可以尝试。
该模型分为三个分支：

1. 运用 OpenPose 这个库，生成 pose 的 18 个 dots，并将这 concat 进 decoder 之前的 feature map 中；
2. 在经过卷积运算后的 feature map 上，运用 mask 将前后景分离，背景的 feature map 也是直接 concat 进最后的 feature map 中；
3. 核心是前景的处理上，用 7 个 ROI 进一步将前景解开，然后用公用的 encoder 生成前景的 feature map。

[笔记链接][8]




[1]: https://www.paperweekly.site/papers/1864
[2]: https://zhuanlan.zhihu.com/p/35626886
[3]: https://www.paperweekly.site/papers/1557
[4]: https://github.com/JoinWei-PKU/PTGAN
[5]: http://www.pkuvmc.com/publications/msmt17.html
[6]: https://zhuanlan.zhihu.com/p/35626478
[7]: https://www.paperweekly.site/papers/1865
[8]: https://zhuanlan.zhihu.com/p/35626735
