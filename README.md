# NightfallProject

**Nightfall Project**'s objective is to transform a photo (for example night to day or rainy to sunny) using machine learning.
This project was developped during a 3-months long internship at CARE Lab (Nara Institute of Science and Technology, Nara, Japan) by a team of two, [@Mohzick](https://github.com/Mohzick) and [@minh-n](https://github.com/minh-n).

## Introduction and motivations

Nightfall Project originally aims to convert a night video into a day video, using an image generating neural network. Transforming night to day has several applications in automated vehicles (to have a clear image of the night, allowing better visibility), surveillance and even tourism or AR attractions. For example, a future tourist will be able to clear rain from a landscape to take the perfect picture. 

This project tackles the basics of machine learning and computer vision. It is mostly a learning experience and reuses the work of Nvidia who developped the main ideas behind the Pix2Pix and CycleGAN machine learning algorithms. 

This project is broadly divided into three parts: in order to train the neural network, I created a dataset composed of various kind of images. Some of them are pairs of day and night images captured by a 360 camera. Some others, like the rain dataset, have been captured by a smartphone and are all unpaired images. The seccond part involves understanding and implementing the Pix2pix and CycleGAN algorithms and creating a model using the dataset. Finally, a real-time application using a PC webcam can be created.

## The application

The final product of this project is a real-time Python application displaying a webcam feed and the processed output of the night-to-day neural network. It is only able to convert the laboratory’s environment because of the very specific training dataset [@minh-n](https://github.com/minh-n) created. 

Here is a video demo of the application:

[![A video demo of the application (youtube)](https://img.youtube.com/vi/Sq3VLYMJ3ts/0.jpg)](https://www.youtube.com/watch?v=Sq3VLYMJ3ts)

## Running the application

### Prerequisites

The conversion application can be runned as is on Linux and needs the following libraries:

```
Python 3.6
CUDA 9.2
PyTorch 0.4
Latest versions of PIL and OpenCV through Python's pip-install
```

The dataset processing scripts only needs `PIL` & `OpenCV`.

### Machine learning 

The Pix2Pix neural network can be trained using a dataset formatted using the available scripts. The dataset needs to be separated into two folders of paired images (Day and Night or any other transformation). The images' size needs to be 350x350. A good number of pairs would be around 1000 (we could only use the 600 available for the final application).  

We ran the training on a desktop PC equipped with a GeForce GTX 1080. Each epoch could take approximately up to 3 minutes, depending on the size of the dataset and its images. The main training script is train.py and can be run in a Linux shell as is. 

## Technologies used

With the help of a programmable cleaner robot and an omnidirectional camera, we have captured many pairs of the corresponding night and day-time images from the same viewpoint.  [![A video of the robot in action](https://img.youtube.com/vi/vov4H4KSB8A/0.jpg)](https://www.youtube.com/watch?v=vov4H4KSB8A)

PyTorch is one of the many machine learning libraries available. Developed by Facebook on top of Torch (a Lua library), it is extensively used across the research world and the industry. 

PyTorch has two advantages for our project: 
-Its syntax is very similar to traditional Python and numpy, making the learning process easier,
-It makes use of CUDA, the GPU acceleration API developed by Nvidia, making the calculation times lower.

That is why we have chosen to work with PyTorch over other libraries like Tensorflow. Furthermore, the 1.0 version of PyTorch will bring a lot of features, including C++ and mobile exports. Those two features are most interesting for our project: a consumer mobile version is the ultimate goal and C++ would only increase its performances. 

## Future work

A standalone Windows app could be developed in order to use it with a Hololens type of device. Other datasets can be created to make the application useable in various kinds of environments. 

## Credits

We would like to thank the team behind Pix2Pix, CycleGAN, PyTorch and CUDA, as well as the teachers and students of CARE Lab. Without them, this whole project would not have been possible. 

