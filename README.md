# Coding3 Final Project
### Aim
I've really thought long and hard about what topic to do for the final project of coding3.Finally,I want to putting a glasses on the cat in image: make it like this 😊 ➡️ 😎

I think the main step to implement is 

1.tracking the cat eyes

（update：1.use the cat face detector model to determine the area of the cat’s eyes）

2.put the images together

（update：2.use in-painting with a diffusion model to replace the cat’s eyes with sunglasses）


### 1.Dataset
At the beginning, I chose the existing database of cat.

Cat Dataset：[https://www.kaggle.com/datasets/crawford/cat-dataset](https://www.kaggle.com/datasets/crawford/cat-dataset)

Cat Face Detection：[https://www.kaggle.com/datasets/gpreda/cat-face-detection](https://www.kaggle.com/datasets/gpreda/cat-face-detection)

<img width="529" alt="截屏2023-06-16 02 17 05" src="https://github.com/CarlyLiu/coding3finalproject/assets/112803802/cf01bfc3-661c-4bad-b6a4-fac32b1806b1">

the coding of download dataset in kaggle

with reference:

https://www.kaggle.com/general/156610

https://www.kaggle.com/general/74235

### 2.1 YOLO model dataset - Image Annotation
Very unfortunately,I got a kaggle dataset of the cat eye ,but it's the points annotation (the yolo model need boxes annotation

That means, I need to do ** manually ** label images:(, which also is a new experience for me, and really take me a long and boring time.

> after this ,i got a idea of ai for label images, We can let the annotation software perform machine learning during the annotation process to predict the annotation label position, which can reduce the annotation time to a certain extent and improve efficiency.

<img width="1470" alt="截屏2023-06-15 22 56 33" src="https://github.com/CarlyLiu/coding3finalproject/assets/112803802/d97cff64-d20d-4f3f-89b9-d2b16d69e4ce">

For good results label at least 300 images, so imanually label of cat eye 300+ images in trainning side and 40 images in test side.

after that, i need to convert the VoTT csv format to the YOLOv3 format.

take me long time to figure out the tutorial of this part which is run in terminal.

[data_train.txt](https://github.com/CarlyLiu/coding3finalproject/files/11765357/data_train.txt)

[data_classes.txt](https://github.com/CarlyLiu/coding3finalproject/files/11765358/data_classes.txt)

### 2.2 train YOLO model







reference:
https://towardsdatascience.com/using-computer-vision-to-find-the-best-cat-photo-from-a-video-fd11c43596b8

https://blog.insightdatascience.com/how-to-train-your-own-yolov3-detector-from-scratch-224d10e55de2

https://www.kaggle.com/datasets/crawford/cat-dataset

https://github.com/iacs-capstone-2020-adoptimize/final_project/tree/master

adam recommend:
yes, that can also be combined:
You can use the cat face detector model to determine the area of the cat’s eyes
You can use in-painting with a diffusion model to replace the cat’s eyes with sunglasses
https://www.timothybrooks.com/instruct-pix2pix/

https://github.com/marando/pycatfd

https://huggingface.co/runwayml/stable-diffusion-inpainting

https://colab.research.google.com/github/huggingface/notebooks/blob/main/diffusers/in_painting_with_stable_diffusion_using_diffusers.ipynb#scrollTo=hvdHYdtTu6KA
