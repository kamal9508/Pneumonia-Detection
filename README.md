# Pneumonia Detection Using CNN Stacked Model

## 📌 Overview

This project focuses on detecting pneumonia from chest X-ray images using a *stacked deep learning model. The stacked model combines three powerful CNN architectures—DenseNet169, **MobileNetV2, and **Xception*—to improve detection accuracy. By leveraging the strengths of these models, the system provides a robust classification mechanism for medical diagnostics.

The goal of this project is to assist healthcare professionals in diagnosing pneumonia more accurately and efficiently by analyzing chest X-ray images.

---

## 🏗 Project Workflow

1. *Pretrained CNN Models*:
   - Feature extraction is performed using three pretrained models: *DenseNet169, **MobileNetV2, and **Xception*.
   - These models are fine-tuned to extract meaningful features from chest X-ray images.

2. *Stacked Model*:
   - The outputs of the three models are combined into a *stacked model*.
   - A final classifier (e.g., fully connected layers) is trained on top of the combined features to classify images as "Pneumonia" or "Normal."

3. *Prediction*:
   - The final stacked model predicts whether a given chest X-ray image indicates pneumonia.

---

## 🛠 Installation

### 1️⃣ Prerequisites
- Python 3.8 or higher
- TensorFlow, Keras, NumPy, Matplotlib, and other dependencies
- GPU (optional but recommended for faster training)

### 1️⃣ Steps to Set Up

1. *Clone the Repository*:
   bash
   git clone https://github.com/your-repo/pneumonia-detection.git
   cd pneumonia-detection
   

2. *Set Up a Virtual Environment* (Optional but Recommended):
   bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   

3. *Install Dependencies*:
   Install the required Python packages using pip:
   bash
   pip install -r requirements.txt
   
   If you don't have a requirements.txt file, you can manually install the necessary packages:
   bash
   pip install tensorflow keras numpy matplotlib scikit-learn pandas
   

4. *Download Dataset*:
   The model is trained on the *Pneumonia Chest X-Ray Dataset*. You can download it from the following sources:
   - *Kaggle*: [Pneumonia Chest X-Ray Dataset](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia)
   
   After downloading, place the dataset in the data/ directory or specify the path in the configuration file:
   bash
   mkdir data
   # Extract the dataset into the 'data/' folder
   

---

## 🚀 Usage

### 1️⃣ Train the Model
To train the stacked CNN model, run the following command:
bash
python train.py

This script will:
1. Load the dataset.
2. Preprocess the images (resizing, normalization, etc.).
3. Extract features using DenseNet169, MobileNetV2, and Xception.
4. Combine the outputs of these models into a stacked model.
5. Train the final classifier on top of the stacked model.

You can customize the training process by modifying the hyperparameters in the config.py file.

### 1️⃣ Evaluate the Model
After training, evaluate the model's performance on the test set:
bash
python evaluate.py

This script will output metrics such as accuracy, precision, recall, and F1-score.

### 1️⃣ Make Predictions
To make predictions on new chest X-ray images, use the following command:
bash
python predict.py --image_path path/to/image.jpg

The script will output whether the image indicates pneumonia or not.

---

## 📊 Results
### 📊 Model Performance  
- **Accuracy**: **92%**  
- **Evaluation Metrics**:  

  | Class | Precision | Recall | F1-Score | Support |
  |-------|-----------|--------|----------|---------|
  | **Normal (0)** | 0.92 | 0.87 | 0.90 | 234 |
  | **Pneumonia (1)** | 0.93 | 0.96 | 0.94 | 390 |
  
- **Macro Average**:  
  - Precision: **0.92**  
  - Recall: **0.91**  
  - F1-Score: **0.92**  

- **Weighted Average**:  
  - Precision: **0.92**  
  - Recall: **0.92**  
  - F1-Score: **0.92**  

### 1️⃣ Confusion Matrix
The confusion matrix shows the number of true positives, true negatives, false positives, and false negatives:
plaintext
[[TN  FP]
 [FN  TP]]

You can visualize the confusion matrix by running:
bash
python visualize_results.py


---

## 🧪 Experimentation

### 1️⃣ Hyperparameter Tuning
You can experiment with different hyperparameters such as learning rate, batch size, and number of epochs by modifying the config.py file.

### 1️⃣ Ablation Study
To understand the contribution of each individual model (DenseNet169, MobileNetV2, Xception), you can run ablation studies by disabling one or more models in the stack.

---

## 🤝 Contributing

Contributions are welcome! If you find any issues or have suggestions for improvement, feel free to open an issue or submit a pull request.

### 1️⃣ Steps to Contribute
1. Fork the repository.
2. Create a new branch (git checkout -b feature/YourFeatureName).
3. Commit your changes (git commit -m 'Add some feature').
4. Push to the branch (git push origin feature/YourFeatureName).
5. Open a pull request.

---

## 📜 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

---

## 🙏 Acknowledgments

- *Dataset*: Thanks to the creators of the [Pneumonia Chest X-Ray Dataset](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia) on Kaggle.
- *Libraries*: This project uses TensorFlow, Keras, and other open-source libraries.
- *Inspiration*: Inspired by research papers and open-source projects on medical imaging and deep learning.