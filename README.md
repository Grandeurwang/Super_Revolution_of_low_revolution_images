# Project3: Super-revolution: Improving revolution of blurry images
![image](figs/example.png)

### [Full Project Description](doc/project3_desc.md)


### Team members (Group 12)
+ Hu, Yiyao yh3076@columbia.edu
+ Wang, Guanren gw2380@columbia.edu
+ Yang, Xi xy2378@columbia.edu
+ Zheng, Fei fz2277@columbia.edu

[**Presentation**](https://https://github.com/Grandeurwang/Super_Revolution_of_low_revoltion_images/blob/master/doc/Presentation%20Project3%20Group12.pptx)

### Background
For this project, we have a set of 1500 pairs of images. For each pair, we have a high-resolution image that serves as the ground truth and a down-sampled low-resolution image as the input for the learning task. The learning goal is to produce a predicted high resolution image as output based on the low-resolution input that is as close to the ground truth as possible.

Suppose that our client is interested in creating an mobile AI program that can enhance the resolution of blurry and low-resolution images.

The portability of this AI program (holding storage and memory cost) and the computational efficiency (test running time cost) are of great concern to your client. This translates to a balance between the complexity of variables/features/models used and the predictive performance.

### Project summary:  
+ In this project, we utilized two algorithms to enhance the resolution of blurry and low-resolution images. We 1) implemented the current practice as the baseline model, 2) implemented an improvement to the current practice, and 3) evaluated the performance gain of your proposed improvement against the baseline. We utilized tensorflow in python as improved model.For baseline model we used `doParallel`,`gbm` and `EBImage` library in R to do super-resolution of the images. We calculated the MSE and PSNR for evaluation purpose. Our model is better than the nerest-neighbor method and bilinear interpolation. Additionally, it is better than bicubic interpolation as well.
+ The MSE and PSNR for baseline model are *0.0028* and *27.4187* respectively, and the MSE and PSNR for improved model are *0.0022* (because R and Python use different scale for RGB, the best way to compare two models is to use PSNR) and *27.8961* respectively, which is obviously better than the baseline models.

### [Workflow for Baseline Model](https://https://github.com/Grandeurwang/Super_Revolution_of_low_revoltion_images/blob/master/doc/Presentation%20Project3%20Group12.pptx)

![image](doc/predictiveprogram.png)


### Comments about training `srgan` model
When use [SRGAN.ipynb](https://github.com/Grandeurwang/Super_Revolution_of_low_revoltion_images/blob/master/doc/SRGAN.ipynb) to run the `srgan` model, just set corresponding `train set path` and `test set path`. Set `validation=Fasle` to use the all the train data to train. Set `n_epoch_init=10` to initialize the model. This might cost about 30 mins locally for each epoch. Set `n_epoch=20` (no less than 10) to train the total `srgan` model. This might cost about 50 mins locally for each epoch.

### Examples of super-revolutioned images by our algorithms:
![image](figs/example1.png)
![image](figs/example2.png)

### Contribution Statement
*Guanren Wang* is responsible for all implementation of the baseline model (GBM) including: deploying Google Cloud VM for parallel computing, feature extraction, cross validation, model training and testing, super-revolution (generate predicted images), final evaluation.

*Fei Zheng* is responsble for all parts of srgan model except the validation.

*Xi Yang* is responsble for README file and code editing, final test and reproduction of the model.

*Yiyao Hu* is responsible for the validation part of srgan model and presentation.

Following [suggestions](http://nicercode.github.io/blog/2013-04-05-projects/) by [RICH FITZJOHN](http://nicercode.github.io/about/#Team) (@richfitz). This folder is orgarnized as follows.

```
proj/
├── lib/
├── data/
├── doc/
├── figs/
└── output/
```

Please see each subfolder for a README file.
