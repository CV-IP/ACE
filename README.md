# ACE
PyTorch code for our arXiv article:

[**Generating Unrestricted Adversarial Images with a Differentiable Color Filter**](https://arxiv.org/abs/2002.01008)

We propose Adversarial Color Enhancement (ACE), an approach that uses a differentiable color filter to create unrestricted adversarial images. This paper validates two properties of the resulting adversarial images: 1) maintained or enhanced **photographic quality and appeal**, even with large perturbations introduced. 2) Higher **transferability** than conventional L<sub>p</sub> and other unrestricted approaches. We also present two potential ways to improve ACE in terms of image quality by guiding it with specific attractive image styles or adapting it toregional semantics.

## Implementation
 
### Requirements
torch>=1.3.1; torchvision>=0.4.2; scipy=1.3.x (**Important!** The 1.4.x releases of scipy have resulted in greater than 100x slow-down of "stats.truncnorm.rvs" relative to the 1.3.x versions when loading Inception-V3 model in PyTorch.)
### Download data

Run [this official script](https://github.com/tensorflow/cleverhans/blob/master/examples/nips17_adversarial_competition/dataset/download_images.py) to download the dataset.

### Generating adversarial examples with ACE

```
python main.py -batch_size 25 -gpu 1 -max_iterations 500 -learning_rate 0.01 -pieces 64 -search_steps 1 -initial_lambda 5
```

### Examples

<br /><br /> -->

<p align="center">
  <img src="https://github.com/ZhengyuZhao/AdvCF/blob/master/figure/ex_2.JPG" width='1000'>
  <img src="https://github.com/ZhengyuZhao/AdvCF/blob/master/figure/ex_3.JPG" width='1000'>
  <img src="https://github.com/ZhengyuZhao/AdvCF/blob/master/figure/ex_4.JPG" width='1000'>
  <img src="https://github.com/ZhengyuZhao/AdvCF/blob/master/figure/ex_6.JPG" width='1000'>
  <img src="https://github.com/ZhengyuZhao/AdvCF/blob/master/figure/ex_7.JPG" width='1000'alt>
  <em>Fig. 2: More examples generated by AdvCF (s=1/64, &lambda;=5). In each group, top: original image, bottom: adversarial image.</em>
</p>
