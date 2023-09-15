# DeepFake Detection

Deepfakes are synthetic media in which a person in an existing image or video is replaced with someone else's likeness. Deep Fakes are increasingly detrimental to privacy, social security, and democracy.They can distort our perception of the truth and hence we need a strategy to improve their detection of the Deepfakes. Here, we have developed some prediction models to efficiently differentiate real and deepfake manipulated videos.


This repository includes 3 .ipynb and corresponding .py files. Each of them implement one of the following 3 face detection techniques - DLIB, MediaPipe and MTCNN. All of these files follow the same procedure as written below.

## Preprocessing:
Frame capturing was done from all the videos such that some number(32) of evenly number of frames were extracted from all the videos. If any video is short, then the number of frames extracted were somewhat lesser than 32.
After that, face detection was performed by 3 different face detection techniques: 1)DLIB 2)MediaPipe 3)MTCNN . All types of images were converted to 64 X 64 X 3 size and stored in the respective arrays.

Example of extracted frames are as follows:

![alt text](https://github.com/HardSavani/DeepFake-Detection/blob/main/illustration.jpeg?raw=true)

=======
## Preprocessing:
Frame capturing was done from all the videos such that some number(32) of evenly number of frames were extracted from all the videos. If any videa is short, then the number of frames extracted were somewhat lesser than 32.
After that, face detection was performed by 3 different face detection techniques: 1)DLIB 2)MediaPipe 3)MTCNN . All types of images were converted to 64 X 64 X 3 size and stored in the respective arrays.


## Data Augmentation:
Data Augmentation is applied by adding noise to the images for classifiers to learn better. Various noises were tried like Gausssian, Speckle and sp noise. Noise useful here was observed to gaussian which was meaningfully blurring the image, rest are not useful here.

## Dimensionality Reduction:

Two dimensionality reduction techniques were used: 1)LDA 2)PCA . Firstly, Standard Scaler was applied on the dataset and then the dimensionality reduction techniques were applied.
Linear discriminant analysis (LDA) is a dimensionality reduction technique used to reduce the number of features to a more manageable number by minimizing the intraclass distances and maximizing the distances between different classes.
Principal Component Analysis, or PCA, is a dimensionality-reduction method that is often used to reduce the dimensionality of large data sets.

## Training and Testing:

Three different classifiers are used to train the dataset and test it on the testing dataset to give accuracy, f1-score and logloss for LDA, PCA and Normal dataset. The three different classifiers used are: 1)SVC 2)MLP 3)KNN.
For each classifier, each type of dataset was trained and testing was performed.

## Comparison:

The comparison for each type of dataset and for each type of classifier was also done with the help of cross validation scores and correspomding boxplots were plotted.

## Additional Classifiers:

### Convolutional Neural Network:

Analysing the state of our results achieved through https://arxiv.org/pdf/2004.07676v1.pdf the picture of convolutional neural network was brought in the project. Different variations of the CNN starting from the basic one and going all through EfficientNet and InceptionResnetV2 were implemented on the dataset provided. The results were analysed and compared with the previous classifiers.

![alt text](https://github.com/HardSavani/DeepFake-Detection/blob/main/Efficient_Net.png?raw=true) | ![alt text](https://github.com/HardSavani/DeepFake-Detection/blob/main/MobileNetV2.png?raw=true)
