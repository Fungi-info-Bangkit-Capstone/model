# ML-Fungi.Info

## Summary

Fungi.info is an app that detects and classify a fungi or mushroom types. We use Tensorflow as we build the model using CNN, where this method is one type of Machine Learning that commonly used for image data. We utilize CNN to do the Image Classification to determine the fungi types and use a pre-trained model called MobileNetV3(Large) to cover a wide range of image classification and to have a small sized model.

This repository mainly consists of 3 (three) files:
1. 'MobileNet Model.ipynb' is the notebook files of this project
2. 'label.txt' is used to store a list of labels or classes used in classification task
3. 'model3.tflite' is machine learning model file that has been converted to .tflite format for the needs of this project

## MobileNet Model.ipynb

### How to make the Model?

1. Run the code on the notebook using <a href='https://colab.research.google.com/'>**Google Colaboratory**</a>
2. Wait for the code training process until 'model3.tflite' finishes downloading automatically.
3. Manually download the label from `File`.

### Modelling Process

1. Building and training a classification model using MobileNetV3Large as a base model.
2. The weights parameter is set to 'imagenet', indicating that the pre-trained weights of the model trained on the ImageNet dataset will be used.
3. `include_top` is set to False to exclude the fully connected layers of the base model.
4. `input_shape` is set to (255, 255, 3).
5. The model is compiled using the Adam optimizer.
6. The loss function is set to `categorical_crossentropy` as commonly used in multi-class classification.
7. The training is performed for 40 epochs with early stop using callbacks.
8. The history of the training is stored in the history variable.

### Model Accuracy and Loss

<a href="https://ibb.co.com/Brb4Zjv"><img src="https://i.ibb.co.com/1d1sqKB/Model-accuracy-and-loss.png" alt="Model-accuracy-and-loss" border="0"></a>

1. Model training stops at the 20th epoch with early stop callbacks after having no increase in the `val_accuracy` value. The value at the last epoch displayed is 0.9121.
2. The `val_loss` value shows a value that decreases at each epoch and at the end of the epoch it shows the number 0.2804.
