<h1>Monet-CycleGan</h1>
Unpaired Image-to-Image translation with CycleGAN

<h3> Note to the viewers: </h3>

This project is still under making and thus this notebook is still incomplete. I will soon complete this. Until then, feel free to look; if you have any suggestions or feedback, kindly post them in the comments. I have given a brief explanation of what I am doing on each step, however, if you have any doubts or need any clarifications, ask me in the comments and I will be happy to answer.

I hope you like my work!

<hr>

<b>Contents</b><a id='top'></a>
1. [Problem description](#pd)
2. [Dataset description](#dd)
3. [Solution approach - Intro to CycleGAN](#sa)
  1.  [What is CycleGAN?](#sa.1)
  2.  [CycleGAN Architecture](#sa.2)
4. [References](#refer)

<hr>
<h1>1. Problem description</h1> <a id='pd'></a>

<center>
<img src='https://www.kaggle.com/competitions/21755/images/header' width=600>
</center>

<br>

> “Every artist dips his brush in his own soul, and paints his own nature into his pictures.”
> 
> \- Henry Ward Beecher

We recognize artists' works through their unique styles, such as colour choices or brush strokes. The “je ne sais quoi” of artists like Claude Monet can now be imitated with algorithms thanks to Generative Adversarial Networks (GANs). In this project, I will bring that style to some photos or recreate the style from scratch!

Computer vision has advanced tremendously in recent years and GANs are now capable of mimicking objects in a very convincing way. But creating museum-worthy masterpieces is thought of to be, well, more art than science. So can (data) science, in the form of GANs, trick classifiers into believing I’ve created a true Monet? That’s the challenge I’ll take on!

A GAN consists of at least two neural networks: a generator model and a discriminator model. The generator is a neural network that creates the images. For this project, I aim to generate images in the style of Monet. This generator is trained using a discriminator.

The two models will work against each other, with the generator trying to trick the discriminator, and the discriminator trying to accurately classify the real vs. generated images.

I want to build a GAN that generates 7,000 to 10,000 Monet-style images.

<hr>
<h1>2. Dataset description </h1> <a id='dd'></a>

The dataset contains four directories: `monet_tfrec`, `photo_tfrec`, `monet_jpg`, and `photo_jpg`.

The `monet_tfrec` and `monet_jpg` directories contain the same Monet painting images, only in different formats. Similarly, the `photo_tfrec` and `photo_jpg` directories contain the same photos. I aim to add Monet style to these images. Other photos outside of this dataset can also be transformed.

<u>Note:</u> It is also possible to generate Monet-style art paintings from scratch using other GAN architectures like DCGAN. But in this project, I am only focusing on transforming the given photos.

<b>Files:</b>

* `monet_jpg` - 300 Monet paintings sized 256x256 in JPEG format
* `monet_tfrec` - 300 Monet paintings sized 256x256 in TFRecord format
* `photo_jpg` - 7028 photos sized 256x256 in JPEG format
* `photo_tfrec` - 7028 photos sized 256x256 in TFRecord format

Although my dataset only includes Monet images, check out [this](https://github.com/junyanz/CycleGAN) dataset for Cezanne, Ukiyo-e, and Van Gogh paintings to run this GAN on.

<hr>
<h1>3. Solution approach - Intro to CycleGAN</h1> <a id='sa'></a>

<h3>3.1 What is CycleGAN?</h3> <a id='sa.1'></a>

From the authors:

> We present an approach for learning to translate an image from a source domain X to a target domain Y in the absence of paired examples. Our goal is to learn a mapping G: X → Y, such that the distribution of images from G(X) is indistinguishable from the distribution Y using an adversarial loss. Because this mapping is highly under-constrained, we couple it with an inverse mapping F: Y → X and introduce a cycle consistency loss to push F(G(X)) ≈ X (and vice versa).

In essence, it maps an image from a source domain to a target domain (e.g., if we are turning horses into zebras, the source domain will be the horse and the target domain is the zebras). In our case, the photos are the source domain and the target domain is the Monet paintings.

<h3>3.2 CycleGAN Architecture</h3><a id='sa.2'></a>


<hr>
<h1>4. References</h1> <a id='refer'></a>

<b>Kaggle Competition:</b>
* [I'm Something of a Painter Myself](https://www.kaggle.com/competitions/gan-getting-started/)

<b>Model references:</b>
* [CycleGAN documentation](https://keras.io/examples/generative/cyclegan/)
* [ArXiv paper](https://arxiv.org/pdf/1703.10593.pdf)
* [Understanding and Implementing CycleGAN in tensorflow](https://hardikbansal.github.io/CycleGANBlog/)
* [GitHub repository](https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix)
* [Introduction to CycleGAN - Monet paintings](https://www.kaggle.com/code/dimitreoliveira/introduction-to-cyclegan-monet-paintings)

<b>Notebooks referred:</b>
* [Monet CycleGAN tutorial](https://www.kaggle.com/code/amyjang/monet-cyclegan-tutorial)
* [Getting started with GANs](https://www.kaggle.com/code/ruchi798/getting-started-with-gans)
