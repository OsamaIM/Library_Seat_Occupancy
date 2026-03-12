<div align="center">

# Real-Time Library Seat Occupancy Detection

*"Smart Campus Seating Optimization via Spatial Logic"*

![Python](https://img.shields.io/badge/Python-3.11-blue?style=flat-square&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-2.5.1-ee4c2c?style=flat-square&logo=pytorch&logoColor=white)
![YOLOv8](https://img.shields.io/badge/YOLOv8-Ultralytics-yellow?style=flat-square)
![OpenCV](https://img.shields.io/badge/OpenCV-Video-green?style=flat-square&logo=opencv&logoColor=white)

</div>

> **ℹ️ Note**
>
> The **core deep learning pipeline and spatial logic layer are 100% complete and tested**. The real-time web application integration (Next.js/ONNX) is currently in active development.

---

## ✨ What is this project?

This system is an AI-powered smart campus solution that helps students find available study spaces while optimizing for social distancing. [cite_start]Unlike standard surveillance models that just count "people," this system uses a custom **Heuristic Spatial Logic Layer** to actively map the relationship between students and furniture, providing highly accurate, real-time occupancy data. [cite: 85, 86]

---

## 🎯 Two Powerful Features

| Spatial Verification ✅ | Social Distancing Optimizer 📏 |
| :--- | :--- |
| *"Is this seat actually taken?"* | *"Where is the safest place to sit?"* |
| Goes beyond basic object detection. Calculates Intersection over Union (IoU) between "person" and "chair". [cite_start]If overlap > 0.30, the seat is occupied. [cite: 126, 127] | [cite_start]Processes detection data to calculate Euclidean distances between available seats, recommending the optimal empty seat. [cite: 93] |
| **Status: Complete** | **Status: Complete** |

---

## 🏗️ System Architecture

[cite_start]*(flowchart)* [cite: 136]
<div align="center">
  <img src="https://via.placeholder.com/800x300.png?text=Upload+Your+Pipeline+Diagram+Here" alt="System Architecture">
</div>

### Data Flow
[cite_start]`Camera Stream` ➔ `YOLOv8 Inference` ➔ `NMS & Bounding Boxes` ➔ `IoU Spatial Logic` ➔ `Euclidean Optimization` ➔ `Live Dashboard` [cite: 140, 146, 147, 148, 149, 150, 152, 153, 154]

---

## 📊 Current Progress

| Component | Status | Progress |
| :--- | :--- | :--- |
| 🪑 **Custom YOLOv8 Training (best.pt)** | ✅ Complete | 100% |
| 📐 **IoU Spatial Logic Layer** | ✅ Complete | 100% |
| 📏 **Distance Recommendation Engine** | ✅ Complete | 100% |
| 🎥 **OpenCV Live Video Dashboard** | ✅ Complete | 100% |
| 🌐 **Next.js Web GUI** | 🚧 In Progress | 20% |
| ⚡ **ONNX Web Browser Inference** | 🚧 In Progress | 10% |

---

## 🛠️ Technology Stack

| Layer | Technology |
| :--- | :--- |
| **Object Detection** | YOLOv8 (Ultralytics) |
| **Deep Learning Framework** | [cite_start]PyTorch 2.5.1 (CUDA 12.1) [cite: 162] |
| **Video Processing** | [cite_start]OpenCV (DirectShow backend) [cite: 163] |
| **Spatial Math** | [cite_start]NumPy & SciPy [cite: 166] |
| **Hardware Tested** | [cite_start]NVIDIA GeForce RTX 3060 (6GB VRAM) [cite: 161] |
| **Dataset** | [cite_start]Roboflow Library-Seat-v2 (2,046 Train / 196 Val images) [cite: 177, 189] |

---

## 📈 Model Performance (Validation Metrics)

[cite_start]The system is highly optimized for edge devices, achieving real-time speeds without sacrificing accuracy. [cite: 110, 111]

| Metric | Score | Timing | Speed (ms/image) |
| :--- | :--- | :--- | :--- |
| **Precision (P)** | [cite_start]0.806 [cite: 192] | **Preprocess** | [cite_start]0.3 ms [cite: 196] |
| **Recall (R)** | [cite_start]0.761 [cite: 192] | **Inference** | [cite_start]3.5 ms [cite: 196] |
| **mAP50** | [cite_start]0.773 [cite: 192] | **Postprocess** | [cite_start]3.7 ms [cite: 196] |

---

## 🚀 Quick Start

```bash
# Clone the repository
git clone [https://github.com/OsamaIM/Library_Seat_Occupancy.git](https://github.com/OsamaIM/Library_Seat_Occupancy.git)
cd Library_Seat_Occupancy

# Install dependencies
pip install -r requirements.txt

# Run the live webcam detection
python main.py
