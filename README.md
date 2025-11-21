# ASL Translator AI – Deep Learning Sign Language Recognition

A complete, end-to-end system for translating American Sign Language (ASL) gestures into letters using a fine-tuned MobileNetV2 deep learning model.
The project includes:

- Training pipeline (with advanced augmentation + fine-tuning)

- Evaluation tools (confusion matrix, metrics, accuracy)

- Real-time prediction using a webcam

- GUI tester (Tkinter-based ASL testing tool)

- Image-based prediction for single images

This project is designed for high accuracy, fast inference, and clean modular code.

## 🚀 Features
### ✔ Training

- Two-phase training (frozen → fine-tuned layers)

- Strong data augmentation

- Regularization (dropout, batchnorm)

- Reduced overfitting, high generalization

### ✔ Evaluation

- Top-1 and Top-5 accuracy

- Classification report (precision, recall, F1)

- Normalized confusion matrix

- CSV logs for model analysis

### ✔ Prediction

- Real-time webcam ASL recognition

- Single image recognition
  
- Auto brightness correction

- Top-3 predictions with confidence

### ✔ GUI (ASL Tester App)

- Load image or use webcam

- Top-3 live predictions

- Confidence bars

- Dark UI theme

## 📁 Project Structure
```
ASL-Translator-AI/
│
├── train_mobilenetv2.py            # Training script
├── evaluate_model.py               # Model evaluation (accuracy, matrix)
├── predict_asl.py                  # Webcam & image prediction
├── test_model.py                   # Tkinter GUI tester
│
├── models/
│   ├── asl_mobilenetv2_improved.h5 # Final fine-tuned model
│   └── best_model.h5               # Best checkpoint
│
├── datasets/
│   ├── asl_alphabet_train/         # Training dataset
│   └── asl_alphabet_test/          # Testing dataset
│
└── README.md
```

## 📦 Installation
1. Clone the repository
```bash
git clone https://github.com/yourusername/ASL-Translator-AI.git
cd ASL-Translator-AI
```
2. Create a virtual environment
```bash
python -m venv venv
source venv/bin/activate   # (Linux/Mac)
venv\Scripts\activate      # (Windows)
```

3. Install dependencies
```bash
pip install -r requirements.txt
```
### 📚 Dataset

This project uses the ASL Alphabet Dataset, containing:

- 87,000+ images

- 29 classes (A–Z + del + space + nothing)

- Real hands captured under multiple lighting conditions

Download dataset from [here](https://www.kaggle.com/datasets/grassknoted/asl-alphabet)


🧠 Training the Model

To train from scratch or fine-tune the model:
```bash
python train_mobilenetv2.py
```

This will:

- Load MobileNetV2

- Train custom ASL layers

- Fine-tune top layers

- Save multiple models:

- best_model.h5

- asl_mobilenetv2_improved.h5

- training_history.png

#### 🧪 Evaluate the Model

To evaluate the model using the test dataset:
````bash
python evaluate_model.py --test-dir datasets/asl_alphabet_test
````

This generates:

- Top-1 accuracy

- Top-5 accuracy

- Confusion matrix → confusion_matrix_normalized.png

- Classification report CSV → classification_report.csv

  🎥 Real-Time Prediction

  Use your webcam to recognize ASL gestures:
```bash
  python predict_asl.py
```

Features include:

- Real-time recognition

- Auto-brightness correction

- Top-3 predictions with confidence

To test a single image:
```bash
python predict_asl.py --image my_image.jpg
```
🖥 ASL GUI Tester

This launches a desktop application for testing ASL gestures:
```
python test_model.py
```

Features:

- Dark theme

- Top-3 predictions with progress bars

- Load image or use webcam

- FPS counter


💡 How It Works
Pipeline Overview
```
Images → Preprocessing → MobileNetV2 Backbone → Classifier → Prediction
```
## Tech Used

- TensorFlow / Keras

- OpenCV

- MobileNetV2 feature extraction

- Tkinter GUI

- Matplotlib + Seaborn

📜 License

MIT License — free to use, modify, and distribute.
