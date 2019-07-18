# Problem and Approach
The dataset we worked on is derived from the Google Landmark Recognition Challenge that took place on Kaggle. The challenge at hand was to build models that classify the images provided in such a way that it matches the correct landmark with each unique image.
![Google Landmark Recognition_Challenge](https://user-images.githubusercontent.com/39646018/60909844-e7427180-a29c-11e9-84c3-4247cf61e4da.png)

We have to classify these landmarks from (15 Thousand!) different classes of landmarks.The landmark recognition training data originally contained over 1.2 million images with around 15K classes.To put things simply, this means that we would require a lot of computing power, coupled with a lot of time and patience. We worked on Nvidia DGX GPU (supercomputer) because of the same.

Another problem we faced is that we were given image URL's, so first we wrote the python script for downloading the images from those URL's and place them into their respective classes.

Now we seperated these folders into 3 parts train(80%), test(10%) and validation(10%) using python script [folder_splitting.py](https://github.com/adityasurana/Google-Landmark-Recognition-Challenge/blob/master/folder_splitting.py)

Top 30classes Train Data:-


![1_aeLjNvJHE1g4HDR5Wp-Cag](https://user-images.githubusercontent.com/39646018/60911074-01ca1a00-a2a0-11e9-846b-953727dcd80b.png)

**After manually scrubbing, we observed that many test images have no landmarks and some have more than one landmark in them.**
![1_UCNb0_y6qvpzBx9FfRCyMA](https://user-images.githubusercontent.com/39646018/60911605-325e8380-a2a1-11e9-8da6-f37fe3bbf597.png)

# ResNet 50

Our first modeling approach was ResNet50, a pre-trained convolutional neural network that is trained on the ImageNet database.

1) The reason we started with this model is twofold:
   ResNet50 is a residual learner, meaning it tries to learn from the residuals as opposed to only learning the contributing features

2) This model aims to solve the oversaturation issue that many neural nets face as network depth increases.

In simple words, ResNet50 subtracts feature information from the input of a layer to learn about the residuals. ResNet50 is a 50 layer Residual Network. 
 
# VGG-16
VGG16, is perhaps one of the most popular convolutional net that is used for Transfer Learning using Keras. It is a 16-layer Covnet used by the Visual Geometry Group (VGG) at Oxford University in the 2014 ILSVRC (ImageNet) competition. 

![0_xJBpXtKndb_WXfSq](https://user-images.githubusercontent.com/39646018/61392041-a02b3080-a8db-11e9-92b2-834331d9829e.png)


