# Driver-Drowsiness Using DeIT Transformer - 99.73 % Accurate 

## Problem Statement 
<p>Driver drowsiness is a critical issue that directly impacts road safety and is a major cause of traffic accidents worldwide. With drivers becoming fatigued, the ability to remain alert while on the road diminishes, leading to slower reaction times and impaired decision-making. As such, detecting signs of drowsiness in drivers can play a pivotal role in preventing these accidents and saving lives. My Project offers an effective method to address this problem. Visual cues such as facial expressions, eye movements, and head orientation are used to detect drowsy drivers in real time.</p>

</br>

## Dataset  

- https://www.kaggle.com/datasets/ismailnasri20/driver-drowsiness-dataset-ddd
- Research Paper - https://doi.org/10.1007/978-981-33-6893-4_6
- More than 41,790 images in total

## Libraries Used
- OpenCV, Torch ,Numpy, Pandas , Seaborn , skitlearn, Transformer, tqdm,random, PIL,  Multiprocessing and Os[AX_NUM_THREADS] to speed up training,

# Brief Workflow

## Data Preparation
- Constructing Filepaths and validating whether all images can be loaded without errors
- Class labelling and combining classes into a unified dataset

## Exploratory Data Analysis
- Display multiple images using grid visualization
- Resize all images to a consistent shape (e.g., 224x224) for downstream modeling
- Checking for any imbalance in data
- Data is randomised to avoid any bias

## Train Preperation 
- Split into train, validation, test (80% train, 10% validation, 10% test)
- Data augmentation and normalization to improve convergence by standardizing pixel values.
- DataLoaders used to manage batching and shuffling which is critical for efficient training and preventing biases.
- Pretrained models like DeiT (Data-efficient Image Transformers) used [ saves time and improves accuracy on a large dataset like ours]

## Model
- DeiT tiny Vision Transformer pre-trained on ImageNet used
- The last layer (classification head) of the model is modified to output probabilities for 2 classes as drowsy vs non-drowsy
- Cross entropy loss and adam optimiser with a learning rate of  with a learning rate of 10^-4, batch processing
- Epochs - 5 ( due to GPU restrictions and large dataset)

## Evaluation 
- Confusion Matrix
- F1 score
- Loss and Accuracy curves

 

<img width="941" alt="Screenshot 2024-12-22 at 3 55 32 PM" src="https://github.com/user-attachments/assets/3ca3258e-48e4-4a18-a683-f9ea1cc87a1e" />

Check Version 1/1 on my kaggle notebook - https://www.kaggle.com/code/ray0911/drowsiness


  
