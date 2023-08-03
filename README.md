## Traffic-Sign-Identifier - Convolutional Neural Network
This Python script implements a Convolutional Neural Network (CNN) capable of identifying 43 different types of road traffic signs with an accuracy of ~97%. The CNN is designed to classify images of road signs into their respective categories, making it useful for applications like autonomous driving, traffic analysis, and road safety. I used the German Traffic Sign Recognition Benchmark, a dataset with around 50,000 images of road signs to train and test this model.
The script uses libraries like tensorflow, cv2, numpy, os, and sys.

### How It Works
The script loads image data from the specified data_directory. Replace data_directory with the path to the directory containing the traffic sign images. It assumes that the data directory has one sub-directory for each category of traffic signs and loads images from these sub-directories. Each image is resized to dimensions IMG_WIDTH x IMG_HEIGHT x 3.

The dataset is split into training and testing sets, and the labels are converted to categorical using tf.keras.utils.to_categorical.

The CNN architecture is defined using TensorFlow's Sequential model. It consists of convolutional layers, max-pooling layers, flatten layer, dense layers, dropout layer, and an output layer with NUM_CATEGORIES units, one for each category. I was cognisant of the computing power of my device when I designed this model so in some cases, accuracy is traded off for speed.

The model is compiled with the Adam optimizer and categorical cross-entropy loss function.

The model is then trained on the training data for a total of 10 epochs.

After training, the model is evaluated on the testing data to measure its performance.

If you provided the optional argument model.h5, the script will save the trained model to the specified file.
