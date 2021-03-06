<div align="center">
  <img width="480px" src="https://research.nvidia.com/sites/default/files/publications/representative_image_512x256.png" alt="Photo credit: Nvidia" />
  
  <i> Plot twist: these people are not real  </i>😲
  (Photo credit: <a href="https://research.nvidia.com/publication/2017-10_Progressive-Growing-of">Nvidia</a>)
</div>

# Generative adversarial networks using Pytorch

## Table of Contents
  - [Models](#models)
    - [Conditional GAN](#cgan)
    - [CT-GAN](#ct-gan)
    - [DCGAN](#dcgan)
    - [GAN](#gan)
    - [InfoGAN](#infogan)
    - [LSGAN](#lsgan)
    - [pix2pix](#pix2pix)
    - [Relativistic GAN](#ralsgan)
    - [Super resolution GAN](#srgan)
    - [Wassterstein GAN](#wgan)
    - [WGAN-GP](#wgan-gp)
  - [Requirements and configuration](#requirements-and-configuration)
  - [Running the models](#running-the-models)
  - [What's the point of this repo?](#whats-the-point-of-this-repo)
  
# Models
### CGAN
> **_[Conditional Generative Adversarial Nets](https://arxiv.org/abs/1411.1784)_** (2014)

[[Code](https://github.com/ozanciga/gans-with-pytorch/tree/master/cgan)]

**_Quick summary_**: CGANs came right after the GANs were introduced. In a regular GAN, you can't dictate specific attributes of the generated sample. For instance, if your GAN generates humans, there is no principled way of forcing the GAN to produce just male faces. CGAN modifies the original GAN by adding a simple condition parameter, so that we can control the certain attributes of the output (such as the digit, rather than just generating any digit).

<div align="center">
<img src="https://github.com/ozanciga/gans-with-pytorch/blob/master/cgan/out/GAN%20output%20%5BEpoch%2080%5D.jpg?raw=true" />
</div>

<div align="right"> <b><a href="#">∧ Go to top</a></b></div>

***





### CT-GAN
> **_[Improving the Improved Training of Wasserstein GANs: A Consistency Term and Its Dual Effect](https://arxiv.org/abs/1803.01541)_** (2018)

[[Code](https://github.com/ozanciga/gans-with-pytorch/tree/master/ct-gan)]

**_Quick summary_**: CT-GANs follow the path opened by the WGANs by adding a regularization term to the loss objective, which gives crisper and more photo-realistic images.

<div align="center">
<img src="https://github.com/ozanciga/gans-with-pytorch/blob/master/ct-gan/out/GAN%20output%20%5BEpoch%2034%5D.jpg?raw=true" />
</div>

<div align="right"> <b><a href="#">∧ Go to top</a></b> </div>

***





### DCGAN
> **_[Unsupervised Representation Learning with Deep Convolutional Generative Adversarial Networks](https://arxiv.org/abs/1511.06434)_** (2015)

[[Code](https://github.com/ozanciga/gans-with-pytorch/tree/master/dcgan)]

**_Quick summary_**: DCGANs introduced convolutional neural networks and encoding & decoding to the GAN sphere. Even today, they are the backbone of almost all of the modern architectures. 

<div align="center">
<img width="180px" height="180px" src="https://github.com/ozanciga/gans-with-pytorch/blob/master/dcgan/out/real_samples.png?raw=true" /> <img width="180px" height="180px" src="https://github.com/ozanciga/gans-with-pytorch/blob/master/dcgan/out/GAN%20output%20%5BEpoch%20358%5D.jpg?raw=true" />
</div>

<div align="center"> <i>(left)</i> Real car images <i>(right)</i> Generated car images </div>

<div align="right"> <b><a href="#">∧ Go to top</a></b> </div>

***





### GAN
> **_[Generative Adversarial Networks](https://arxiv.org/abs/1406.2661)_** (2014)

[[Code](https://github.com/ozanciga/gans-with-pytorch/tree/master/gan)]

**_Quick summary_**: The paper that started everything. Generative adversarial nets are remarkably simple generative models that are based on generating samples from a given distribution (for instance images of dogs) by pitting two neural networks against each other (hence the term adversarial). One network tries to generate more realistic dog images while the other tries to distinguish between real images and the images generated by this network. They both learn to do their jobs better as time goes on (i.e. as training progresses) and hopefully in the end the generative network gets so good at its job the generated images are indistinguishable from the real ones.

<div align="center">
<img src="https://github.com/ozanciga/gans-with-pytorch/blob/master/gan/out/GAN%20output%20%5BEpoch%2095%5D.jpg?raw=true" />
</div>

<div align="right"> <b><a href="#">∧ Go to top</a></b> </div>

***


### InfoGAN
> **_[InfoGAN: Interpretable Representation Learning by Information Maximizing Generative Adversarial Nets](https://arxiv.org/abs/1606.03657)_** (2016)

[[Code](https://github.com/ozanciga/gans-with-pytorch/tree/master/infogan)]

**_Quick summary_**: CGANs try to give apriori information during training to set a specific attribute of the generated image (e.g. the digit in MNIST generation). But how about we just want to get some intrinsic characteristic of the image that we don't want to supply? Maybe we just want to generate digits that are slanted over a certain direction or are wide or narrow. InfoGANs basically figure out these attributes in an unsupervised manner and let us tune it afterwards (so for instance we can generate only italic digits etc).  

<div align="center">
<img width="240" height="240" src="https://github.com/ozanciga/gans-with-pytorch/blob/master/infogan/out/(Nothing%20is%20varied)%20GAN%20output%20%5BEpoch%2014%5D.jpg?raw=true" /> <img width="240" height="240" src="https://github.com/ozanciga/gans-with-pytorch/blob/master/infogan/out/(Only%20vary%20c1)%20GAN%20output%20%5BEpoch%2014%5D.jpg?raw=true" /> <img width="240" height="240" src="https://github.com/ozanciga/gans-with-pytorch/blob/master/infogan/out/(Only%20vary%20c2)%20GAN%20output%20%5BEpoch%2014%5D.jpg?raw=true" />
</div>

<div align="center">
<i>(left)</i> Nothing is varied <i>(middle)</i> only c<sub>1</sub> is varied <i>(right)</i> only c<sub>2</sub> is varied
</div>

<div align="right"> <b><a href="#">∧ Go to top</a></b> </div>

***







### LSGAN
> **_[Least Squares Generative Adversarial Networks](https://arxiv.org/abs/1611.04076)_** (2017)

[[Code](https://github.com/ozanciga/gans-with-pytorch/tree/master/lsgan)]

**_Quick summary_**: LSGANs introduced a simple modification to the GAN objective function that proved itself to be more stable which yields higher quality images. LSGANs found application in later papers to generate high quality images in even more complex tasks. 

<div align="center">
<img src="https://github.com/ozanciga/gans-with-pytorch/blob/master/lsgan/out/GAN%20output%20%5BEpoch%2011%5D.jpg?raw=true" />
</div>

<div align="right"> <b><a href="#">∧ Go to top</a></b> </div>

***



### pix2pix
> **_[Image-to-Image Translation with Conditional Adversarial Networks](https://arxiv.org/abs/1611.07004)_** (2016)

[[Code](https://github.com/ozanciga/gans-with-pytorch/tree/master/pix2pix)]

**_Quick summary_**: Use a reference image (can be an annotation mask, a natural scene image that we want to turn the daytime into night, or even sketches of shoes), and change it to a target image. Here, we see the labels of roads, buildings, people etc turned into actual cityscapes just from crude and undetailed simple color masks. 

<div align="center">
<img src="https://raw.githubusercontent.com/ozanciga/gans-with-pytorch/master/pix2pix/out/GAN%20output%20%5BEpoch%20216%5D.jpg"  />
<img src="https://raw.githubusercontent.com/ozanciga/gans-with-pytorch/master/pix2pix/out/GAN%20output%20%5BEpoch%20240%5D.jpg"  />
</div>

<div align="right"> <b><a href="#">∧ Go to top</a></b> </div>
---




### RaLSGAN
> **[The relativistic discriminator: a key element missing from standard GAN](https://arxiv.org/abs/1807.00734)** (2018)

[[Code](https://github.com/ozanciga/gans-with-pytorch/tree/master/ralsgan)]

**_Quick summary_**: Unlike any previous model, this GAN is able to generate high resolution images (up to 256 x 256) from scratch relatively fast. 
Previously, people either stuck to resolutions as low as 64 x 64, or they have [progressively increased the resolution](https://arxiv.org/abs/1710.10196) which
takes a long time. 

<div align="center">
<img src="https://raw.githubusercontent.com/ozanciga/gans-with-pytorch/master/ralsgan/out/GAN%20output%20%5BIteration%2031680%5D.png" />
<img src="https://raw.githubusercontent.com/ozanciga/gans-with-pytorch/master/ralsgan/out/GAN%20output%20%5BIteration%2031616%5D.png" />
</div>

<div align="right"> <b><a href="#">∧ Go to top</a></b></div>


***

### SRGAN
> **[Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network](https://arxiv.org/abs/1609.04802)** (2017)

[[Code](https://github.com/ozanciga/gans-with-pytorch/tree/master/srgan)]

**_Quick summary_**: Take a low resolution image and increase its resolution (e.g. VHS -> 4K quality).

<div align="center">
<img width=362 height=215 src="https://github.com/ozanciga/gans-with-pytorch/blob/master/srgan/out/GAN%20output%20%5BEpoch%206%5D%20(1).jpg?raw=true" /> <img width=362 height=215 src="https://github.com/ozanciga/gans-with-pytorch/blob/master/srgan/out/GAN%20output%20%5BEpoch%206%5D.jpg?raw=true" />
</div>

<div align="center">
<i>(top)</i> Low resolution image <i>(middle)</i> Original high resolution image <i>(bottom)</i> Super resolution image reconstructed from the top image
</div>


<div align="right"> <b><a href="#">∧ Go to top</a></b> </div>

***



### WGAN
> **_[Wasserstein GAN](https://arxiv.org/abs/1701.07875)_** (2017)

[[Code](https://github.com/ozanciga/gans-with-pytorch/tree/master/wgan)]

**_Quick summary_**: This paper proves that there are cases which the regular GAN objective function (which minimizes the binary cross entropy) fails to converge for certain distributions. Instead of matching two distributions, it explores the idea of moving parts of one distribution to the another to make two distributions equal. The metric of "how much of the distribution A do I have to push around to get B" is called the Wasserstein distance (Earth mover's distance).

<div align="center">
<img width=180 height=180 src="https://github.com/ozanciga/gans-with-pytorch/blob/master/wgan/out/bn_GAN%20output%20%5BEpoch%2099%5D.jpg?raw=true" /> <img width=180 height=180 src="https://github.com/ozanciga/gans-with-pytorch/blob/master/wgan/out/no_bn_GAN%20output%20%5BEpoch%2099%5D%20(1).jpg" />
</div>

<div align="right"> <b><a href="#">∧ Go to top</a></b> </div>

***
***




### WGAN-GP
> **_[Improved Training of Wasserstein GANs](https://arxiv.org/abs/1704.00028)_** (2017)

[[Code](https://github.com/ozanciga/gans-with-pytorch/tree/master/wgan-gp)]

**_Quick summary_**: Wasserstein GANs introduced a more stable loss function but the Wasserstein distance calculation is computationally intractible. Therefore they work with an approximation of it, where the assumptions they made to implement the network requires a cap on the magnitude of gradients. In order to make sure the network is stable, they clip values which causes information loss. WGAN-GP instead adds a regularization term to force the norm of the gradients to be around 1, which naturally shapes the network to learn without having to lose information to ensure stability. 

<div align="center">
<img width=180 height=180 src="https://github.com/ozanciga/gans-with-pytorch/blob/master/wgan-gp/out/GAN%20output%20%5BEpoch%2052%5D.jpg?raw=true" /> <img width=180 height=180 src="https://github.com/ozanciga/gans-with-pytorch/blob/master/wgan-gp/out/GAN%20output%20%5BEpoch%20105%5D.jpg?raw=true" />
</div>

<div align="right"> <b><a href="#">∧ Go to top</a></b> </div>

***


## Requirements and configuration 
I started doing this work with <b>[Pytorch](https://pytorch.org/) 0.4.0</b> and <b>Python 3.6</b> 
(with <b>[Cuda](https://developer.nvidia.com/cuda-downloads) 9.0</b> and 
<b>[CuDNN](https://developer.nvidia.com/cudnn) 7</b>), with <b>Ubuntu 16.04</b>. 
Around right after "SRGAN"s, I switched to <b>Pytorch 0.4.1</b>, 
<b>Cuda 9.2</b> and <b>[CuDNN](https://developer.nvidia.com/cudnn) 7.2</b>. 
For visualizing the GAN generation progress on your browser, you will need the facebook's <b>[visdom](https://github.com/facebookresearch/visdom)</b> library.

I recommend using [anaconda3](https://conda.io/docs/user-guide/install/download.html) to install dependencies and 
<b>[Pycharm](https://www.jetbrains.com/pycharm/)</b> community version to edit the code.
For dataset, I provide either scripts or links. Although I prefer using datasets included in
Pytorch whenever I can for simplicity, there is only so much you can do with digits or CIFAR images. Still, I stick to 
previously used datasets to cut off my implementation time, where the data acquisition and preparation takes easily 
more than 60-70% of the time.

## Running the models
First, you need to start up the visdom, and then most of the time, it is easy as just running the script. Sometimes, you might need to download some custom dataset for a given paper. In that case, I usually put some comments at the beginning of the model file. A complete example:
```
python -m visdom.server
bash download_dataset.sh cityscapes
python pix2pix.py
```

## What's the point of this repo? 
I am aware that the internet is riddled with high quality implementations of any paper that is covered (or to be covered in the future) here. The only purpose of this repository is to be educational, and by educational I mean to educate me. Before this project, I was mainly a Keras/Tensorflow user and I only started dipping my toe on Pytorch very recently. I now love the dynamic construction, easy debugging and all that. In addition, generative adversarial networks are great to practice the latest computer vision models in deep learning because they use something from everything. 

On this note, please let me know if there is any model you'd like to see implemented. Don't hesitate to call me out on the bugs, stupid mistakes I've made, Pytorch tips like how to use memory more efficiently etc. I am constantly learning new things, and half of the comments on the code are me trying to figure out the things or notes to myself because I haven't quite understood some aspect of the model.
