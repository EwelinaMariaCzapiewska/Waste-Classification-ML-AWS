Waste Classifier with Explainable AI 
A cloud-native machine learning system developed to automate waste sorting. The project leverages Computer Vision, Transfer Learning, and Explainable AI (XAI) to classify trash into 6 categories while visualizing the model's decision-making process.
![alt text](wykresy.png)
<!-- Tutaj możesz też wgrać screena z Gradio -->
🚀 Key Features
Cloud-Native Training: Model trained using Amazon SageMaker and Amazon S3 (AWS Academy).
Transfer Learning: Utilizes the MobileNetV2 architecture for high efficiency and low latency.
Explainable AI (Grad-CAM): Generates real-time heatmaps to show exactly which parts of the image influenced the classification.
Live Web Interface: Interactive UI built with Gradio for instant webcam-based testing.
🏗️ Tech Stack
Language: Python
Deep Learning: TensorFlow, Keras
Cloud: AWS (S3, SageMaker)
Interface: Gradio
Analysis: Grad-CAM (Gradient-weighted Class Activation Mapping), OpenCV
📊 Dataset & Training
Data Source: Garbage Classification Dataset (Kaggle).
Categories (6): Cardboard, Glass, Metal, Paper, Plastic, Trash.
Preprocessing: Images resized to 224x224px, normalized, and split 80/20 (Train/Validation).
Optimizer: Adam.
Loss Function: Sparse Categorical Crossentropy.
Accuracy: Achieved ~71% on training and ~67% on validation after 5 epochs.
🔍 Explainable AI (XAI) Analysis
The integration of Grad-CAM allowed us to verify the model's focus.
Observation: The model effectively ignores the user's face and background noise, focusing on the edges and textures of the waste object.
Interesting Case: Shiny chocolate wrappers were classified as "Metal" due to their reflective properties, proving the model analyzes physical textures rather than just semantic shapes.
🛠️ How to run
Open the Klasyfikacja_Odpadow_AWS.ipynb in your Jupyter/SageMaker environment.
Ensure the pre-trained model file model_odpady_final.h5 is in the same directory.
Run the installation cell: %pip install gradio tensorflow opencv-python.
Run the Load Model and Gradio Interface cells.
Click the generated .gradio.live link to start the live camera demo.
⚠️ Challenges & Future Improvements
Domain Shift: The model was trained on studio images but tested in real-world lighting.
Future Scope: Implementing Data Augmentation and Fine-tuning deeper layers of the network to increase accuracy beyond 90%.
Detection Integration: Moving from image classification to Object Detection (e.g., YOLO) to isolate objects from complex backgrounds.
