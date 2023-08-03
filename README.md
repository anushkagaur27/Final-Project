# Final-Project - Dog Allergy Detection
Hi my name is Anushka Gaur and my final project was a dog allergy detector. This model 
classifies whether a specific dog is hypoallergenic or not. This model uses a CNN(Convolutional Neural Network) 
through the jetson-nano. It also uses resnet-18 and imagenet to train and classify the images. My mode is made through
transfer learning, or the re-training of an already existing model.

# Real World Impact
In the real world, people all over the world suffer from allergies, whether they are severe or not. In some cases, some people
risk fatality due to allergies. Dog allergies are not uncommon, and dog hairs can easily cause irritation to people. Hypoallergenic dogs
are dogs that do not shed excessive hair (or if hairless, no hair at all). If my model was to be more accurate and easier to use,
this model could help people avoid being around or adopting dogs that potentially could cause allergic reactions.

# The Algorithm
As stated before, my model was created using jetson nano and the jetson-inference library in Visual Studio Code. There are two classes
that the images can be potentially sorted into: Hypoallergenic, or Non-Hypoallergenic. The dataset that I used from Kaggle was used to re-train 
the already existing model train.py. Afterwards, the model was converted into an ONNX formatting. To process the images for classification,
I used imagenet. 

# Reproducing This Project
1) Make sure that you have downloaded all the files from this github repository. To do so, click on the green code button on the right
hand sign of this page. Download the zip file and unzip all the files onto your deskptop.
2) If not done already, clone the jetson-inference library to have all the necessary files for this model and your jetson nano. Do so by using the command
"git clone --recursive https://github.com/dusty-nv/jetson-inference".
3) Download the necessary python packages if not done so already by using the command "sudo apt-get install libpython3-dev python3-numpy"
