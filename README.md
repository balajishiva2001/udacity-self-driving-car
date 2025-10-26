🏎️ Self-Driving Car Simulation using CNN

This project demonstrates how to train a Convolutional Neural Network (CNN) to autonomously drive a car in a simulator environment. It follows an end-to-end deep learning approach — from importing and preprocessing driving data to training, validating, and saving a steering angle prediction model.

------------------------------------------------------------
🚀 Project Overview
------------------------------------------------------------
This notebook trains a model to predict steering angles from road images using a deep learning model inspired by NVIDIA’s End-to-End Learning for Self-Driving Cars architecture. The model learns to drive by mapping road images captured from a car simulator to the corresponding steering angles.

------------------------------------------------------------
🧩 Features
------------------------------------------------------------
- Data preprocessing and balancing to avoid bias toward straight driving.
- Real-time data augmentation (zoom, pan, brightness, flipping) for robustness.
- CNN-based model to predict steering angles from front-facing camera images.
- Visualization of training vs validation loss.
- Model checkpoint saved as model7.h5.

------------------------------------------------------------
🛠️ Tech Stack
------------------------------------------------------------
- Python 3.x
- Google Colab / Jupyter Notebook
- TensorFlow / Keras
- NumPy, Pandas, Matplotlib
- OpenCV
- imgaug (for augmentation)

------------------------------------------------------------
📁 Project Structure
------------------------------------------------------------
```
carSimulation/
├── driving_log.csv           # Driving data (image paths + steering angles)
├── IMG/                      # Folder containing driving images
├── carSimulation.ipynb       # Main notebook
├── model7.h5                 # Saved trained model
└── README.txt                # Project documentation
```
------------------------------------------------------------
🧠 Model Architecture
------------------------------------------------------------
The CNN model includes:
- 5 Convolutional layers with ELU activations
- Flatten layer
- Fully connected layers (100 → 50 → 10 → 1 neurons)
- Adam optimizer (lr=0.001)
- Mean Squared Error (MSE) as the loss function

------------------------------------------------------------
🧪 Training Summary
------------------------------------------------------------
Training Samples: ~2554
Validation Samples: ~639
Epochs: 50
Batch Size: 40
Loss (Final): ≈ 0.085
Validation Loss (Final): ≈ 0.07–0.08

------------------------------------------------------------
🧰 How It Works
------------------------------------------------------------
1. Data Loading – Reads driving_log.csv and imports image paths and steering angles.
2. Data Balancing – Removes excessive straight-driving samples for uniform distribution.
3. Data Augmentation – Random pan, zoom, brightness, and flipping transformations.
4. Preprocessing – Crop, convert RGB→YUV, Gaussian Blur, resize to (66, 200), normalize.
5. Training – Uses a generator to yield augmented images in batches.
6. Model Saving – Trained model is saved as model7.h5.

------------------------------------------------------------
📊 Visualization
------------------------------------------------------------
The notebook plots training vs validation loss to monitor overfitting and convergence.

------------------------------------------------------------
▶️ How to Run
------------------------------------------------------------
1. Upload your dataset (driving_log.csv + IMG/) to Google Drive.
2. Mount your drive in Colab:
   from google.colab import drive
   drive.mount('/content/drive')

3. Update the dataset path in the notebook:
   path = '/content/drive/MyDrive/Colab Notebooks/myData1'

4. Run all cells sequentially to import, balance, train, and save the model.

------------------------------------------------------------
📦 Output
------------------------------------------------------------
- Trained model: model7.h5
- Training curve plot: Loss vs Epochs

------------------------------------------------------------
📈 Future Improvements
------------------------------------------------------------
- Integrate real-time steering control in a simulator.
- Add dropout layers for better regularization.
- Use multiple camera angles (Left/Right) for correction.
- Implement real-time inference using OpenCV.

------------------------------------------------------------
🧑‍💻 Author
------------------------------------------------------------
Balaji Shiva  
GitHub: https://github.com/balajishiva2001
