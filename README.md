# Final Project - Dog Allergy Detection
Hello, my name is Anushka and my final project was a dog allergy detector. This model 
classifies whether a specific dog is hypoallergenic or not. This model uses a CNN (Convolutional Neural Network) 
with the jetson-nano. It also uses resnet-18 and imagenet to train and classify the image dataset of dogs. My model is made using
transfer learning, or the re-training of an already existing model.

## Real World Impact
In the real world, people all over the world suffer from allergies, whether they are severe or not. In some cases, some people
risk fatality due to allergies. Dog allergies are not uncommon, and dog hairs can easily cause irritation to people. Hypoallergenic dogs
are dogs that do not shed excessive hair (or if the dog is hairless, no hair at all). If my model was to be more accurate and easier to use,
this model could help people avoid being around or adopting dogs that potentially could cause them allergic reactions.

![alt text](https://github.com/anushkagaur27/Final-Project/assets/141268862/f293088a-8da5-4c0b-a015-ecbf1cb0da21)

## The Algorithm
As stated before, my model uses the jetson nano and the jetson-inference library in visual studio code. There are two classes
that the images can be potentially sorted into: Hypoallergenic, or Non-Hypoallergenic. The dataset that I used from Kaggle was used to re-train 
the already existing model, train.py, in the jetson-inference library using resnet-18. Afterwards, the model was converted into an ONNX formatting. To process the images for classification, I used imagenet. 

![alt text](https://github.com/anushkagaur27/Final-Project/assets/141268862/8f61d6a6-4366-4271-b7ad-ab4984e0c7ca)

## Reproducing This Project
1) Make sure that you have downloaded all the files from this github repository. To do so, click on the green code button on the right
hand sign of this page. Download the zip file and unzip all the files onto your deskptop. Also, download additional files using these links: https://drive.google.com/file/d/1jhkAOswI1X0AfbZCJxuCbSKJ6eJtfXYH/view?usp=sharing https://drive.google.com/file/d/17UpEV8gsf4Gng7UhLGMH_p1tnaGfLcSm/view?usp=sharing 
2) If not done already, clone the jetson-inference repository to have all the necessary files for this model in your jetson nano. Do so by using the command "git clone --recursive https://github.com/dusty-nv/jetson-inference".
3) Download the necessary python packages if not done so already by using the command ```sudo apt-get install libpython3-dev python3-numpy```
4) Create a build directory using the command ```mkdir build```
5) Use the command ```cd build``` to navigate into the new build directory. In this directory, use the command ```cmake ../```
6) Navigate into vsCode or your desired terminal. Make sure that your jetson nano is connected.
7) Navigate into the directory ```cd jetson-inference/python/training/classification/models```
8) Download the resnet18.onnx file, the model_best.pth.tar file, the tensorboard file, and the labels.txt file(all the files within the models folder) into this directory.
9) Navigate into the data direcotry by using the commands ```cd ../``` followed by ```cd data```
10) Dowload the dataset into this directory. Unzip the files using the command ```tar xvzf dog_breeds.tar.gz```
11) Use the command ```cd ../``` to navigate back to the classification directory. Now that you have all of the necessary files downloaded into your jetson-inference library, we can now process the images and classify them individually.
12) Set your network and dataset variables for classification using the commands ```NET=models/dog_breeds``` and ```DATASET=data/dog_breeds```
13) To run the model with an image to classify, use the command ```imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 labels=$DATASET/labels.txt $DATASET/test/$DIRECTORY/$IMAGE.jpg $DESIRED.jpg``` where $DATASET is not to be changed(it is used for the dataset variable that we already
set), $DIRECTORY being the name of the directory that the image to be classified is under, and $DESIRED being the name that you want your classified image to take on.
14) To see the final classified image with a classification label and accuracy rate, download the image file from your terminal into imageWriter.

## Final Words
This model is an AI machine learning model that utilizes the concept of convolutional neural networks. Overall, I am not entirely satisfied with my model, as it has some major fundamental issues with its training. If I had had more time to work on this project I would have mainly focused on creating a more concise dataset to train more accurately(run more epochs). 

# Classification Model Demonstration
[Dog Allergy Classifier Demonstration Video](https://youtu.be/8ILD8d3ttj4)
