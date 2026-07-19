CIFAR-10 Object Classification using ResNet50

## Overview
A transfer learning project that classifies images into 10 object categories 
from the CIFAR-10 dataset, using a pretrained ResNet50 model as the feature extractor.

  Dataset
- CIFAR-10: 60,000 32x32 color images across 10 classes
  (airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck)
- Images upsampled to match ResNet50's expected input size

  Model Architecture
- Base: ResNet50 (pretrained on ImageNet, frozen)
- Preprocessing: 3x UpSampling2D layers to scale up CIFAR-10's small images
- Custom head: Flatten → BatchNorm → Dense(128, relu) → Dropout(0.5) 
  → BatchNorm → Dense(64, relu) → Dropout(0.5) → BatchNorm → Dense(10, softmax)

  Training
- Optimizer: RMSprop (learning_rate=2e-5)
- Loss: sparse_categorical_crossentropy
- Epochs: 10

  Results
- Training accuracy: 57.5% (epoch 9)
- Validation accuracy: 79.15% (epoch 8)
- [Add your loss/accuracy plots here as images]

How to run
1. Clone this repo
2. Install requirements: pip install -r requirements.txt
3. Run the notebook in Jupyter or Google Colab

Tech stack
Python, TensorFlow/Keras, ResNet50, NumPy, Matplotlib, OpenCV
