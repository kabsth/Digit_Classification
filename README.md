#  Handwritten Digit Classification Using k-NN (from Scratch)

This project implements a **k-Nearest Neighbors (k-NN)** classifier from scratch in Python to recognize handwritten digits using a subset of the **MNIST dataset**. The goal is to understand how basic classification models work without relying on high-level libraries like scikit-learn.

---

##  Objective

- Build a simple but functional digit classifier using the k-NN algorithm
- Understand each step of the classification pipeline (loading, preprocessing, prediction, evaluation)
- Manually split and process data for better conceptual clarity
- Avoid black-box tools to promote foundational understanding

---

##  Project Contents

| File Name                  | Description                                      |
|---------------------------|--------------------------------------------------|
| classification_task.ipynb| Jupyter notebook with full implementation         |
| requirements.txt        | Required Python packages                         |
| mnist_test.csv          | Dataset used (CSV of pixel values)               |

---

## Dataset Details

- Format: CSV file with 785 columns per row
  - Column 0: Digit label (0–9)
  - Columns 1–784: Pixel values of a 28x28 image (flattened)
- Sample size used:
  - 500 rows for training
  - 100 rows for testing

---

## Thought Process & Reasoning

###  Why k-NN?
I chose k-Nearest Neighbors because it's an **intuitive, easy-to-understand algorithm** that uses distance to make decisions. It helps grasp how classification works based on closeness to known data.

###  Why Implement From Scratch?
Rather than using pre-built models from scikit-learn, I wrote the algorithm manually to:
- Understand how Euclidean distance is calculated
- Implement the idea of “majority voting”
- Learn how model predictions work at the lowest level

###  Why Manual Data Splitting?
Instead of using train_test_split:
- I **manually selected** the first 500 samples as training data and the next 100 as test data
- This gave me better control and understanding of which samples were being used for each purpose
- It also avoided the need for extra libraries and made the notebook cleaner for learning

###  Why Normalize Pixel Values?
- Original pixel values range from 0–255
- Dividing by 255 scales them to 0–1
- This makes Euclidean distance calculations more stable and meaningful

---

##  Step-by-Step Workflow

1. **Load Data**
   - Used pandas to read the CSV file
   - Extracted features and labels separately

2. **Preprocessing**
   - Normalized pixel values (X = X / 255.0)
   - Manual train-test split (500 training, 100 testing)

3. **Visualization**
   - Used matplotlib to display sample digits
   - Helped verify the correctness of data before prediction

4. **Implement k-NN Classifier**
   - Created a KNNClassifier class
   - Used Euclidean distance to find the nearest neighbors
   - Predicted labels by majority vote of k nearest neighbors

5. **Prediction & Evaluation**
   - Predicted labels for the test set
   - Compared them to actual labels
   - Calculated **accuracy (79%)**
   - Visualized a few predictions with actual labels

---

##  Accuracy & Observations

- Accuracy on test set: **~79%**
- Good performance considering:
  - Small training set
  - No feature engineering
  - Basic distance metric
- Accuracy could improve with:
  - Larger training set
  - Better distance metrics (e.g., Manhattan, cosine)
  - Dimensionality reduction

---

##  Technologies Used

- numpy — numerical operations
- pandas — data handling
- matplotlib — data visualization
- collections.Counter — for majority vote logic
- **No machine learning libraries used** — k-NN written manually

---

## ▶️ How to Run

1. **Clone the repository**
   
bash
   git clone https://github.com/kabsth/Digit_Classification.git

2. **Install dependencies**

bash
  pip install -r requirements.txt

3. **Open the notebook**
classification_task.ipynb

Run all cells
