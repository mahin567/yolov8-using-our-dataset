YOLOv8 Using Custom Dataset

This project demonstrates how to train and evaluate a YOLOv8 object detection model using a custom dataset. It provides a complete pipeline from dataset preparation to model training and inference.

📌 Overview

YOLOv8 (You Only Look Once v8) is a state-of-the-art object detection model developed by Ultralytics. It is designed to be fast, accurate, and easy to use for real-time detection tasks .

In this project, we:

Train YOLOv8 on a custom dataset
Perform object detection
Evaluate model performance
Run inference on new images
🧠 Features
✅ Custom dataset training
✅ Easy-to-follow structure
✅ Fast inference with YOLOv8
✅ Supports GPU/CPU execution
✅ Clean and modular code
📂 Project Structure
yolov8-using-our-dataset/
│── data/                # Dataset (images & labels)
│── runs/                # Training results
│── models/              # Model weights
│── train.py             # Training script
│── detect.py            # Inference script
│── dataset.yaml         # Dataset configuration
│── requirements.txt     # Dependencies
⚙️ Installation
Clone the repository:
git clone https://github.com/mahin567/yolov8-using-our-dataset.git
cd yolov8-using-our-dataset
Install dependencies:
pip install -r requirements.txt

Or install YOLOv8 directly:

pip install ultralytics
📊 Dataset Preparation

YOLOv8 requires the dataset in this format:

dataset/
│── images/
│   ├── train/
│   ├── val/
│── labels/
│   ├── train/
│   ├── val/

Each image must have a corresponding .txt label file in YOLO format.

Example dataset.yaml:

train: data/images/train
val: data/images/val

nc: 2
names: ["class1", "class2"]
🏋️ Training the Model

Run the training script:

yolo task=detect mode=train model=yolov8n.pt data=dataset.yaml epochs=50 imgsz=640
model: Pretrained YOLOv8 model (n, s, m, l, x)
epochs: Number of training iterations
imgsz: Image size
🔍 Inference (Detection)

Run detection on an image:

yolo task=detect mode=predict model=runs/detect/train/weights/best.pt source=your_image.jpg
📈 Results

After training, results will be saved in:

runs/detect/train/

Includes:

📊 Training graphs
📦 Best model weights
🖼️ Prediction outputs
🧪 Evaluation
yolo task=detect mode=val model=best.pt data=dataset.yaml

Metrics:

mAP (mean Average Precision)
Precision & Recall
💡 Use Cases
Object detection (traffic, people, animals, etc.)
Smart surveillance systems
Industrial automation
Academic research projects
📚 How It Works

YOLOv8 uses a single-stage detection pipeline, meaning it predicts bounding boxes and class probabilities in one pass, making it extremely fast and efficient .

🤝 Contributing

Contributions are welcome!
Feel free to fork the repo and submit a pull request.

📜 License

This project is open-source and available under the MIT License.

👨‍💻 Author

Mahin
GitHub: https://github.com/mahin567

⭐ Acknowledgements
Ultralytics YOLOv8
Open-source computer vision community
