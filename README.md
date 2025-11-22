# Practical Lab 3: Vanilla CNN and Fine-Tune VGG16 - for Dogs and Cats Classification

##  Project Members:
    1. Jarius Bedward #8841640

## Project Summary:

This project is about working with a common practice of deep learning engineers. The project is about taking a existing model
and fine-tunning it to the specifics needed by the engineer. In the project a custom neural network is also created and is compared 
to the fine-tuned model. The project takes 2500 images of cats and dogs and classifies them using the custom model and existing model and 
compares the results and metrics.

**Key Features:**
- **Data Preprocessing:**
  - Load kaggle cats & dogs dataset filled with cats and dogs images
  - Reduces train dataset going from 25,000 images to 5000 images (2,500 of each) and organizes them into specific directories labeld
  - Splits dataset into train and test saving 1000 from the 25,000 images for test
- **Exploratory Data Analysis:**
  - A count of images that are present per class is performed
  - Distribution of cats & dogs visualized through barplot and widths and heights visualized through histogram
  - Sample images from each class are shown
  - Analysis of image size (width & height)
  - 
- **Custom Neural Network**
  - A vanilla CNN is defined with convolutional, pooling, dense and dropout layers
  - Trained on the reduced dataset with validation split for overfitting
  - The best model is saved later using callbacks
- **Fine-Tuned VGG16:**
  - Pre-trained VGG16 model (trained on imageNet) is loaded
  - The top layers are replaced with custom desne and dropout layers for binary classification
  - Trained with validation to prevent overfitting
  - The best version is saved for later
- **Model Evaluation:**
  - Compares the performance of the custom network and VGG16
  - Evaluate models using a list of different metrics including accuracy, confusion matrix, precision, recall, F1-score and percision-recall curves
  - Displays misclassified images to help further understand the models weakness
  - 

## Requirements:
    - pip install -r requirements.txt

##  🎯  How to Run:

1. Clone this repo (git clone <repo-url> cd <repo-folder)
2. Install Required Dependencies: "pip install -r requirements.txt"
3. Open the jupyter notebook
4. Run all the cells within the notebook


## Code Explanation/Workflow:

1. **Import Libraries**
   - We import the libraries for data manipulation (pandas, numpy), plotting (matplotlib, seaborn), image processing, and deep learning (tensorflow, keras) are imported
   - sklearn metrics are imported for evaluation (accuracy, precision, recall, F1-score)
   
2. **Load Dataset**
   - The dataset used is Kaggle's Cats & Dogs dataset
   - It is loaded from local directory
3. **Dataset Reduction** 
   - Original dataset contains 25,000 images. It is reduced to a magnagable size of 5000 train and 2000 test
   - Images are randomly sampled per class and moved to labeled directories
4. **Exploratory Data Analysis**
   - Analyze number of images per class
   - Visualize class distribution and images sizes
   - Shows sample images 

5. **Custom Neural Network**
   - A CNN is defined, compiled and trained
   - Training uses a validation split and a callback to save the best model (best_model.h5)
   - Training and validation accuracy/loss are plotted and displayed to monitor overfitting
   
6. **VGG16**
   - Pre-trained VGG16 is loaded without its top classifier
   - New densee layers are added for binary classification
   - Model is compiled, trained and the best one is saved
   
7. **Model Evaluation**
   - Saved models are loaded
   - Models are valuated on the test set using accuracy, confusion matrix, precision, recall, F1-score and precision-recall curves
   - Display misclassified examples and analyze them to understand model limitations


### Final Conclusion: 
    - Both the custom CNN and fine-tuned VGG16 accuratley classify cats and dogs. VGG16 seems to overall slightly outperforms the CNN due to the pre trained features
    however by analyzing the graphs and the stats, after a while the custom CNN can get even more accurate than VGG16 by the tenth epoch. Despite this, 
    the average metrics over the test set still are in favvor of VGG16. Misclassifgications occur mainly with blurry or partial iamges. 
    Overall, the pre-trained model offers better performance and faster convergence overall. 
    The custom CNN is still valauble for experimaentation and can get to the level of the pre trained model with time.

🤝 Contributing
This is a Practical Lab developed for CSNC8010. If any questions arise do not hesitate to contact the project member.