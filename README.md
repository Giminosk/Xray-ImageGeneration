# Image generation of chest X-ray with GAN

[Generative adversarial network (GAN)](https://en.wikipedia.org/wiki/Generative_adversarial_network) - is a machine learning model, consisting of two parts: a `generator` and a `discriminator`. The generator generates data, while the discriminator tries to distinguish generated and real data, thus the discriminator acts as a complicated loss function for the generator. Our goal is the generator that creates synthetic data undistinguished from real. All this enables the model to learn in an unsupervised manner. 

## About work
In this project I've tried to create artificial chest x-ray images using [this dataset](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia). I trained generator to create 800x800 px grayscale image from random noise, while discriminator was trained on this generated images and 300 real images of healthy people  

## Results
All training process took 11 hours, it consisted of 4000 epoches.  
The gif showing each 100s epoch result:  
<img src="/images/training.gif" width="500" height="500"/>  
A few generated images of final model:  
<img src="/images/result/result0.png" width="300" height="300"/>
<img src="/images/result/result3.png" width="300" height="300"/>
<img src="/images/result/result6.png" width="300" height="300"/>
<img src="/images/result/result8.png" width="300" height="300"/>  

## Conclusions
The resulting images can easily be counted as a chest x-ray, but they are easy to distinguish in comparison with the real ones. The generated images have too much noise and are too blurry, they do not have very clear structures. However, the result is acceptable. It's hard to say what needs to be improved, a more complex generator or more training time (also use a larger dataset than 300 images). Most likely all together.  

`Remark`: as far images from dataset contained letters *R*, the model tried to fit this. It can be noticed on gif of training process.

## File structure
- `image-generating` is main code with models  
- `tests` is code testing final model and generating gif  
- `images` is folder with training images  
  - `result` is subfolder with result images  
- `models` is folder with `generator` and `discriminator` subfolders of saved models  

`Remark` main part of generator was to large to upload it here, [link to drive](https://drive.google.com/file/d/14CtLHrXRM-sEMqMxC5q4UL_JvHcytwp2/view?usp=share_link)
