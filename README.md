### Group Project 5: Choose-your-own-adventure Hackathon

**EXECUTIVE SUMMARY**

We've chosen the Intel Image Classification Kaggle challenge for our hackathon. More details can be found [here](https://www.kaggle.com/datasets/puneet6060/intel-image-classification), but essentially, it's a challenge to classify 150x150 color images of natural features among 6 target classes. We will try a variety of approaches to see how high we can get our classification accuracy. Ideally, we would like to achieve an accuracy of over 80%.

The notebook for this project is available [here](./project-5.ipynb).

---
**MODELING**

- In all, we tried over 12 different models amongst us, with strategies including:
  - Varying numbers of convolution filters, layers, FNN neurons, and training epochs
  - Regularization via L2, Dropout and EarlyStopping
  - Image augmentation using RandomFlip, RandomRotation and RandomZoom
  - Use of AveragePooling layers in place of MaxPooling
  - Pre-trained models for transfer learning

**RESULTS**
- Our 3 best models were:
  - A typical Keras CNN with one Conv2D layer (8 filters) and one FNN layer of 64 neurons with L2 regularization, achieving validation accuracy of **0.74** with minimal overfitting.
  - A Keras CNN with with two Conv2D layers (16 and 64 filters, respectively) and AveragePooling2D layers instead of the usual MaxPooling2D layers, with a single-hidden-layer FNN of 32 neurons, achieving validation accuracy of **0.76** with some overfitting - this model would probably benefit from regularization.
  - A Keras FNN using the VGG19 pretrained dataset for transfer learning, then moving that data through 2 hidden layers of 128 and 64 neurons respectively, achieving our best accuracy of **0.86** with minimal overfitting.
  - The most prevalent misclassifications across all of our models were: street vs. buildings, mountain vs. glacier, and glacier vs. sea.

**CONTRIBUTORS**
- Gabe Mangiante
- Injung Ahn
- Gleb Radchenko
