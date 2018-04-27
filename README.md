# CVPR-2018-Reading

[Unsupervised Person Image Synthesis in Arbitrary Poses][1]

#Image Synthesis
CVPR 2018 Spotlight 论文，ReID + GAN 换 pose。

本文用了较多的篇幅讲 loss function，pose 的提取用的是 OpenPose 这个库。 
其 loss 分为三部分： 

1. Image Adversarial Loss：即传统 GAN 的 loss；

2. Pose Loss：pose 差异，生成后的图片再用 OpenPose 提取 pose 信息做差值；

3. Identity Loss：此为关键，又分为两部分，分别是 content 和 style loss，其中 content 用于保证生成图和原图在某 pretrain model 生成的 feature map 一致， style 则是利用 Gram matrix 生成某种 feature map，然后作比对。


[笔记链接][2]

[1]: https://www.paperweekly.site/papers/1864
[2]: <https://zhuanlan.zhihu.com/p/35626886>
