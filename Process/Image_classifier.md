# Image classification


📁 **WEEK 3**: [02a_image_classifier_pytorch.ipynb](https://git.arts.ac.uk/24006172/Critical-Coding-3-Assigments/blob/main/Week%203/02a_image_classifier_pytorch.ipynb)
📁 **WEEK 4**: [02_transfer_learning.ipynb](https://git.arts.ac.uk/24006172/Critical-Coding-3-Assigments/blob/main/Week%204/02_transfer_learning.ipynb)

📁 **Image classification**: [Image classifier](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/tree/main/Image_classifier)

## CNN Classifier & Transfer Learning Classifier

To organize my image dataset, I experimented with image classifiers. My goal was to categorize the Pop Art–style images I had downloaded into two classes: those containing human figures and those without.
To achieve this, I explored two approaches: a CNN Classifier built from scratch and a Transfer Learning Classifier based on a pre-trained model.
Through this process, I found that the Transfer Learning Classifier produced more accurate results, especially when working with a limited amount of data. It proved to be more effective for small-scale learning tasks compared to the CNN model trained from scratch.

## CNN Classifier

![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/33%20CNN.png)

## Transfer Learning Classifier

![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/33%20transfer.png)


However, the dataset I used in my project was manually curated. Since the amount of data I needed was relatively small, I chose to sort the images by hand. This was necessary because the dataset as a whole was too unstructured for a machine learning model to categorize effectively—at least not with a standard image classification approach.
Given that I only used around 300 images, it was feasible to complete the sorting manually and use the curated dataset to train my classification models.

![qtree-9](https://git.arts.ac.uk/24006172/Critical-Coding-3-Finalproject/blob/main/IMAGE/33%20hand.jpg)


When I initially considered using machine learning for image classification, I overlooked the fact that I didn’t have any labeled Pop Art category data. Because of this, I had no choice but to manually label the images and use them to train the classification model.
This experience also made me realize that if I want to classify specific visual styles—such as posters—it is very difficult to find publicly available datasets that come with ready-made category labels.
However, the model I trained this time should now be capable of handling certain classification tasks related to Pop Art–style images.



