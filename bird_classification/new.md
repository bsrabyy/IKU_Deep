# Bird Classification

testing.. 


## Dataset used

24497 Train, 900 Test, 900 Validation images 224X224X3 jpg format
https://www.kaggle.com/gpiosenka/100-bird-species


## Dataset 
Data set of 180 bird species. 24497 training images, 900 test images(5 per species) and 900 validation images(5 per species.
All images are 224 X 224 X 3 color images in jpg format. Also includes a "consolidated" image set that combines the training, test and validation images into a single data set. This is useful for users that want to create their own training, test and validation sets.
Images for each species are contained in a separate sub directory. Convenient if you use Keras flow from directory as a means to input the data.
Images were gather from internet searches by species name. Once the image files for a species was downloaded they were checked for duplicate images using a python duplicate image detector program I developed. All duplicates detected were deleted in order to prevent their being images common between the training, test and validation sets.
After that the images were cropped so that the bird occupies at least 50% of the pixel in the image. Then the images were resized to 224 X 224 X3 in jpg format. The cropping ensures that when processed by a CNN their is adequate information in the images to create a highly accurate classifier. All files were also numbered sequential starting from one for each species. So test images are named 1.jpg to 5.jpg. Similarly for validation images. Training images are also numbered sequentially with "zeros" padding. For example 001.jpg, 002.jpg ….010.jpg, 011.jpg …..099.jpg, 100jpg, 102.jpg etc. The zero's padding preserves the file order when used with python file function and Keras flow from directory.
The training set is not balanced, having a varying number of files per species. However each species has at least 100 training image files. This imbalanced did not effect my kernel classifier as it achieved over 98% accuracy on the test set.
One significant imbalance in the data set is the ratio of male species images to female species images. About 80% of the images are of the male and 20% of the female. Males typical are far more diversely colored while the females of a species are typically bland. Consequently male and female images may look entirely different.Almost all test and validation images are taken from the male of the species. Consequently the classifier may not perform as well on female specie images.
Also included in the data set is a trained model file BIRDS-224-175-98.62.h5 and a text fileBIRDS-175.txt. These files are used in association with a companion Predictor program which uses these files to make predictions on input images using the trained model. A folder predictor test set contains 101 test images that the Predictor program can predict on. I will post the predictor program shortly. Finally there is a file error list-98.62.txt which shows the list of errors on the test set the model had on the 875 test images.



