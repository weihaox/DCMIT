# DCMIT
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.5](https://img.shields.io/badge/python-3.6-green.svg)](https://www.python.org/)
[![PyTorch 1.0](https://img.shields.io/badge/pytorch-1.0-green.svg)](https://pytorch.org/)


Pytorch implementation of Elsevier Neural Networks **Unsupervised Multi-Domain Multimodal Image-to-Image Translation with Explicit Domain-Constrained Disentanglement**.

Authors: **Weihao Xia**, Yujiu Yang, Jing-Hao Xue.

Contact: xiawh3@outlook.com

We propose explicit disentanglement learning constraints with domain supervision, which investigates how to extract domain supervision information so as to learn explicit disentangled representations to avoid the confusion of content and style.

This work is done in March 2019. The original code was lost after my graduation. But it would not be so difficult to implement the intra-domain translation module based on the inter-domain translation. Furthermore, this module is to make the disentanglement of style and content more accurate, the content loss can be act as a similar role, as demonstrated in our paper.

## Datasets

We use three multi-domain datasets for experiments: Art, Weather, Season. Notice that all images in these datasets are not paired.

Art: This dataset contains four domains: real images, Monet, Ukiyoe and Van Gogh. These art images can be downloaded from [Wikiart](https://www.wikiart.org/) and the real photos are from Flickr with tags landscape and landscapephotography. We use the datasets of monet2photo, vangogh2photo, ukiyoe2photo and cezanne2photo collected by [CycleGAN](https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix).

Weather: This dataset contains four domains: sunny, cloudy, snowy and foggy, which is randomly selected from the [Image2Weather](https://www.cs.ccu.edu.tw/~wtchu/projects/Weather/index.html).

Season: This dataset consists of approximately 6000 images of the Alps mountain range scraped from Flickr. The original dataset collected by [ComboGAN](https://github.com/AAnoosheh/ComboGAN) categorizes photos individually into four seasons based on the provided timestamp of when it was taken. But this lead to many misclassifications. We revise each category by deleting ambiguous images or misclassified images to the right category to make them more distinguishable.

The different domains in a dataset should be placed in folders "trainA, trainB, ..." in the alphabetical order.

<p align="center">
  <img src="/asserts/data-samples.png">
</p>

## Example Results

<p align="center">
  <img src="/asserts/art_d4_result.png">
</p>

<p align="center">
  <img src="/asserts/compare_season_results.png">
</p>

<p align="center">
  <img src="/asserts/deblur_ours.jpg">
</p>

**Unsupervised Multi-Domain Multimodal Image-to-Image Translation with Explicit Domain-Constrained Disentanglement.**</br>
*Weihao Xia, Yujiu Yang, Jing-Hao Xue.*</br>
Neural Networks. (IF= 5.789, JCR Q1, CCF B)

If you found our paper or code useful, please cite our paper.
```
@article{xia2020dcmit,
  author    = {Weihao Xia and Yujiu Yang and Jing-Hao Xue},
  title     = {Unsupervised Multi-Domain Multimodal Image-to-Image Translation with Explicit Domain-Constrained Disentanglement},
  year      = {2020},
  journal   = {Neural Networks}
}
```

## Acknowledgments

Our original code borrows heavily from [DRIT](https://github.com/HsinYingLee/DRIT). Since [HsinYingLee](http://vllab.ucmerced.edu/hylee/) has released the multi-modal multi-domain version, we just include their implementation as submodule.