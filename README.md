 
## 📚 Dataset

The CIFAR-10 dataset contains 60,000 color images (32x32 pixels) divided into 10 classes:

- airplane
- automobile
- bird
- cat
- deer
- dog
- frog
- horse
- ship
- truck

In this project:
- The model is first trained on 5 classes: airplane, automobile, bird, cat, and deer.
- Then, the last layer(s) of the network are retrained to classify the other 5 classes: dog, frog, horse, ship, and truck.

## 🧠 Method

- A pre-trained InceptionV3 model is used for transfer learning.
- Two strategies were tested:
  1. Freeze all layers except the output layer.
  2. Freeze all layers except the fully connected and output layers.

### Results

- **Trainable Parameters**:
  - Strategy 1: ~262,917
  - Strategy 2: ~263,109

- **Accuracy**:
  - Strategy 1: ~93% (train and validation)
  - Strategy 2: ~94% (train), ~94.5% (validation)

- Strategy 2 performed better due to more layers being fine-tuned, allowing better adaptation to the new classes.

## Why Fine-Tuning is Faster

Fine-tuning is faster than full training because most layers are frozen and do not require gradient calculations. This reduces the computational load significantly.


## Libraries Used

- TensorFlow / Keras
- NumPy
- Matplotlib





