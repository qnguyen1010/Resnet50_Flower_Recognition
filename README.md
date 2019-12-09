# Resnet50_Flower_Recognition

This notebook utilizes Resnet 50 in Flower Classification.

Full code: **Flower_Recognition_QN.ipynb**

**Data Pipeline**

1. Use ImageDataGenerator with preprocess_input from keras.applications and validation_split to perform image preprocessing and splitting into traing and validation sets.

2. Load data into Train and Validation sets using ImageDataGenerator with **flow_from_directory**


**Importance**

    When using pretrained model, we should use preprocess_input imported directly from keras.applications as our preprocessing_function in the ImageDataGenerator. This is to prepare our images in accordance with the input format of the pretrained model. No need to use rescale = 1/255

    Use validation_split in ImageDataGenerator to split train/val set. Subset: "training" for train set; "validation" for val set


**Build a model**

We use ResNet50, pretrained weights from Imagenet, and remove the top layers with include_top = False. Pretrained layers are not frozen, we continue to fine tune them.

**Train model**

Trained for 10 epochs, val_acc reaches 0.9214

**Confusion Matrix and Classification Report on Validation set**

See the code for more information
