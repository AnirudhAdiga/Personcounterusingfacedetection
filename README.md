# Personcounterusingfacedetection
method that detects the faces of the people using MTCNN  and identifies them using the VGGFace face recognition model as it yields the most desirable results. computes the number of entries and exits of people.
An appropriate model is used to accomplish this task. These feature vectors are then arranged in such a manner that the same faces are kept in close proximity. This is achieved using a suitable distance measure such as the cosine or the euclidean distance. 
Finally, whenever a new image is passed as input to the classifier, it computes the distance of that image from all the already stored feature vectors(embeddings) and identifies the input as the image that corresponds to its nearest feature vector. As previously communicated in the introduction section, we employ the VGG Face model with the neural network architecture VGG16 for accomplishing this task. This model rose to prominence after the Oxford University paper titled, “Very deep convolutional neural network based image classification using small training sample size”[12], was published. The breakthrough insight offered by that paper was that a significant improvement on the prior-art configurations could be achieved by pushing the depth of the existing neural architectures to 16–19 weight layers. A brief elucidation on the working of the VGG16 model, and how we have utilized it to aid in our project are summed up in the succeeding paragraphs.
The architecture of the VGG16 model consists of very small convolution filters of size 3x3, and a stack of convolutional layers. The convolution stride is set to one pixel. The stack of convolutional layers is closely followed by three fully connected layers, each with a relu activation function, and an output layer containing the softmax activation function[12].
For our project, we borrowed the VGG16 architecture from Keras[13]. Using transfer learning[14][15], we manipulated the model to suit our dataset. Afterward, the dataset was trained with the modified model to obtain the feature vectors. To identify the person, we then utilized the cosine distance measure to arrange the vectors. With a suitable threshold, we defined an is_match() function and identified the faces. This step concludes the first phase implementation of the project.
