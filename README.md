# AutoPilotAI Algorithm using YOLOv8

## 📌 **Project Overview**

This project implements a self-driving car algorithm using YOLOv8 for object detection and obstacle recognition. The model is trained to identify objects from a custom dataset using transfer learning.

## 🚀 **Features**

- Dataset preprocessing and splitting (Train: 70%, Validation: 20%, Test: 10%)
- YOLOv8-based object detection
- Custom training with adjustable parameters
- Model evaluation and performance analysis

## 🛠️ **Tech Stack**

- Python
- YOLOv8 (Ultralytics)
- scikit-learn
- torch
- shutil

## 📂 **Project Structure**
```text
Self-Driving-Car-Algorithm/
├── data/
│   ├── train/
│   ├── val/
│   ├── test/
│   └── data.yaml
├── images/
├── labels/
├── Algorithm.ipynb
├── yolov8n.pt (Pretrained model)
└── README.md
```

## 🧑‍💻 **Installation**
Install dependencies:
```bash
pip install ultralytics torch scikit-learn
```

Download the YOLOv8 model:
```bash
wget https://github.com/ultralytics/assets/releases/download/v0.0.0/yolov8n.pt
```

## ⚙️ **Dataset Preparation**

- Place your images in the `images/` folder and labels in the `labels/` folder.
- Ensure the `data.yaml` file specifies the correct paths.
- Run the preprocessing script to split the dataset:

## 📈 Results
The model will save the trained weights as yolov8n_trained.pt.
Evaluation metrics like mAP and loss curves will be available in runs/train/exp.

## 🤝 Contributing
Contributions are welcome! Feel free to fork the repo and submit a pull request.

## 🛡️ License
This project is licensed under the MIT License.
