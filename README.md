# Mask-Detector
INTRODUCTION TO THE PROJECT-

In this project I have made Mask Detector, which is an example of object detection model. I have made this project using opencv and pytorch. First a dnn model is trained on dataset containing masked and non-masked people, then the model is used to detect mask on the faces of person. The output is an image with a bounding box around face and a label called - "WithMask" for people wearing mask and other label called "WithoutMask" for people not wearing a mask.

LET'S SEE THE STEPS OF THIS PROJECT-

STEP1- 1- DOWNLOADING THE DATASET AND IMPORTING ALL THE NECESSARY LIBRARIES:- The dataset used here can be downloaded from Kaggle. Go to this link- https://www.kaggle.com/ashishjangra27/face-mask-12k-images-dataset. Imported all the libraries necessary- torch,torchvision, numpy, cv2 , pillow and matplotlib.pyplot.

STEP2- 2- PREPARING THE DATASET:- Loaded trainloader and testloader after performimg the transformations required for RESNET-50.

STEP3- 3- BUILDING THE MODEL:- Loaded RESNET50 model and added some extra layers for getting 2 output nodes at last layer.

STEP4- 4- TRAINING THE MODEL:- Trained the model on trainset with ADAM optimizer and learning rate equal to 0.001. After training got the model with test accuracy of 99.9% which shows our model is trained efficiently to work on test data.

STEP5- 5- BULDING THE MASK DETECTOR FUNCTION AND TESTING ON OUTSIDE IMAGES:- Created a mask detector function which takes image path as argument. The image is passed to this function and then by using HAAR CASCADE CLASSIFIER we detected the faces in the image and then passed this cropped image to the model to predict its label. After getting label an output image is returned which contain bounding boxes and labels around the faces. The HAAR CASCADE Classifier is machine learning based approach where a cascade function is trained from a lot of positive and negative images. It is then used to detect objects in other images. Here we have used it to detect faces of human by using haarcascade_frontalface_default.xml. After creating the function, passed image to get the detection.
