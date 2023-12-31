# Final Project - Dog Allergy Detection
Hello, my name is Anushka and my final project was a dog allergy detector. This model 
classifies whether a specific dog is hypoallergenic or not. The main concept that my model focuses on is CNN (Convolutional Neural Networks) 
using the jetson-nano. It uses resnet-18 and imagenet to train and classify the image dataset of dogs. This model also mainly focuses on transfer learning, or the re-training of an already existing model.

## Real World Impact
In the real world, people all over the world suffer from a vast variety of allergies, both severe and not. In some cases, some people
risk fatality due to strong allergies. Dog allergies are not uncommon, and dog hairs can easily cause irritation to people. Hypoallergenic dogs
are dogs that do not shed excessive hair (or if the dog is hairless, no hair at all). If my model was to be more accurate and easier to use,
this model could help people avoid being around or adopting dogs that potentially could cause them allergic reactions.

![alt text](https://github.com/anushkagaur27/Final-Project/assets/141268862/f293088a-8da5-4c0b-a015-ecbf1cb0da21)

## The Algorithm
As stated before, my model uses the jetson nano and the jetson-inference library in visual studio code. There are two classes
that the images can be potentially sorted into: Hypoallergenic, or Non-Hypoallergenic. The dataset that I reorganized from Kaggle was used to re-train 
the already existing model, train.py, in the jetson-inference library using resnet-18. I trained my model for a total of 30 epochs for about 70% accuracy. Afterwards, the model was converted into an ONNX formatting. To process the images for classification, I used imagenet. 

![alt text](https://github.com/anushkagaur27/Final-Project/assets/141268862/8f61d6a6-4366-4271-b7ad-ab4984e0c7ca)

## Reproducing This Project
1) Make sure that you have downloaded all the files from this github repository. To do so, click on the green code button on the right
hand sign of this page. Download the zip file and unzip all the files onto your deskptop. Also, download additional files using these links: https://drive.google.com/file/d/1jhkAOswI1X0AfbZCJxuCbSKJ6eJtfXYH/view?usp=sharing https://drive.google.com/file/d/17UpEV8gsf4Gng7UhLGMH_p1tnaGfLcSm/view?usp=sharing 
2) If not done already, clone the jetson-inference repository to have all the necessary files for this model in your jetson nano. Do so by using the command ```git clone --recursive https://github.com/dusty-nv/jetson-inference```
3) Download the necessary python packages if not done so already by using the command ```sudo apt-get install libpython3-dev python3-numpy```
4) Create a build directory using the command ```mkdir build```
5) Use the command ```cd build``` to navigate into the new build directory. In this directory, use the command ```cmake ../```
6) Navigate into vsCode or your desired terminal. Make sure that your jetson nano is connected.
7) Navigate into the correct directory by using the command ```cd jetson-inference/python/training/classification/models```
8) Download the resnet18.onnx file, the model_best.pth.tar file, the tensorboard file, and the labels.txt file into this directory.
9) Navigate into the data direcotry by using the commands ```cd ../``` followed by ```cd data```
10) Dowload the dataset into this directory. Unzip the files using the command ```tar xvzf dog_breeds.tar.gz```
11) Use the command ```cd ../``` to navigate back to the classification directory. Now that you have all of the necessary files downloaded into your jetson-inference library, we can now process the images and classify them individually.
12) Set your network and dataset variables for classification using the commands ```NET=models/dog_breeds``` and ```DATASET=data/dog_breeds```
13) To run the model with an image to classify, use the command ```imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 labels=$DATASET/labels.txt $DATASET/test/$DIRECTORY/$IMAGE.jpg $DESIRED.jpg```, where $DATASET is not to be changed(it is used for the dataset variable that we already
set), $DIRECTORY being the name of the directory that the image is to be classified under, and $DESIRED being the name that you want your classified image to take on.
14) To see the final classified image with a classification label and accuracy rate, download the image file from your terminal into imageWriter.

## Final Words
This model is an AI machine learning model that utilizes the concept of convolutional neural networks and transfer learning. I fundamentally got to learn and understand how to train AI models. I am proud of how I properly formatted my model and trained it to 70% confidence. However, I am not entirely satisfied with the training of my model as it has some fundamental issues, for example, incorrectly classifying an image with a very high confidence rate. If I had had more time to work on this project I would have mainly focused on creating a more concise dataset to train more accurately (run more epochs) to get more accurate results. 

# Classification Model Demonstration
[Dog Allergy Classifier Demonstration Video](https://youtu.be/8ILD8d3ttj4)
