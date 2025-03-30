# AutoPilotAI Algorithm using YOLOv8

## 📌 **Project Overview**

This project implements a self-driving car algorithm using YOLOv8 for object detection and obstacle recognition. The model is trained to identify objects from a custom dataset using transfer learning.

![Self-Driving Car Algorithm](https://github.com/Akarshjha03/AutoPilotAI/blob/main/Screenshot%202025-03-30%20154148.png)

---

## 🚀 **Features**

- Dataset preprocessing and splitting (Train: 70%, Validation: 20%, Test: 10%)
- YOLOv8-based object detection
- Custom training with adjustable parameters
- Model evaluation and performance analysis

---

## 📝 YOLO Summary

- **Input Image:** (608, 608, 3)
- The input image passes through a **CNN (Convolutional Neural Network)**, resulting in a **(19, 19, 5, 85)** dimensional output.
- After flattening the last two dimensions, the output becomes a volume of shape **(19, 19, 425)**.

### 📦 Understanding the Output:
- Each cell in the **19x19** grid provides **425 values**.
- **425 = 5 x 85** where:
  - **5** represents predictions for **5 bounding boxes**, corresponding to **5 anchor boxes**.
  - **85** consists of:
    - **5 values** for  
      - \( p_c \) - Objectness score  
      - \( b_x, b_y, b_h, b_w \) - Bounding box coordinates  
    - **80 values** representing class probabilities for the detected object.

### ✂️ YOLO’s Final Output
To determine the final detection results, YOLO applies the following post-processing steps:

1. **Score-Thresholding:**  
    - Discard boxes where the class detection score is **below the threshold**.

2. **Non-Max Suppression (NMS):**  
    - Calculate the **Intersection over Union (IoU)** to eliminate overlapping boxes, keeping only the most confident predictions.

This results in the final set of bounding boxes, class labels, and confidence scores, providing an accurate object detection output.

---

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

---

## 🤝 Contributing
Contributions are welcome! Feel free to fork the repo and submit a pull request.

## 🛡️ License
This project is licensed under the MIT License.
