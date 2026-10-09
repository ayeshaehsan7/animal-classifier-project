# Animal Image Classifier (10 classes)

A convolutional neural network (CNN) that classifies photos into 10 animal
categories, built with TensorFlow/Keras in Google Colab.

**Dataset:** Animals-10 (Kaggle), about 26,000 images. Class names are in
Italian: cane (dog), cavallo (horse), elefante (elephant), farfalla
(butterfly), gallina (chicken), gatto (cat), mucca (cow), pecora (sheep),
ragno (spider), scoiattolo (squirrel).

Notebook: [animal_classifier.ipynb](animal_classifier.ipynb)

## Results

| Model | Training acc. | Validation acc. |
|---|---|---|
| v1: baseline CNN (10 epochs) | 93.9% | 62.5% (peak 65.5%) |
| v2: + data augmentation + dropout (15 epochs) | 68.9% | **68.4%** |

## What I learned
- v1 overfit: training accuracy reached 94% while validation accuracy peaked
  at 65.5% and then declined, and validation loss rose from 1.13 to 2.19.
  The model was memorizing the training images.
- For v2 I added data augmentation (random flips, rotations, zoom) and
  dropout. The gap between training and validation accuracy closed
  (68.9% vs 68.4%) and validation accuracy improved to 68.4%.
- v2 was still improving at epoch 15, so it probably hasn't converged.

## What I'd try next
- Train v2 for more epochs.
- Try transfer learning with a pretrained model (e.g. MobileNetV2).
- Look at a confusion matrix to see which animals get mixed up.

## Why I built this
I enjoy coding and technology, and I wanted to move from learning programming concepts to actually building something with machine learning. This was my first ML project, and it taught me that a model with 94% training accuracy can still do poorly on new data, which is what led me to try augmentation and dropout.
## Tools
Python, TensorFlow/Keras, Google Colab
