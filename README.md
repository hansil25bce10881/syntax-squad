# syntax-squad
# 🚙 Offroad Semantic Scene Segmentation

### Duality AI – GHR 2.0 Hackathon

## 📌 Project Overview

This project named enviroNet.seg implements a **semantic scene segmentation model** for off-road autonomy using synthetic desert environments generated from Duality AI’s Falcon digital twin platform.

The goal is to train a model that accurately labels every pixel in an image into terrain/object classes (trees, bushes, rocks, sky, etc.) and generalizes well to **unseen desert environments**.

Semantic segmentation is critical for unmanned ground vehicles (UGVs) to perform obstacle avoidance and path planning.

---

## 🎯 Objectives

* Train a robust semantic segmentation model on the provided dataset
* Evaluate performance on unseen test images
* Optimize accuracy and generalization
* Report **IoU score**, loss curves, and failure cases

---

## 🗂 Dataset

The dataset contains synthetic RGB images and pixel-wise ground-truth labels.

### Classes

| ID    | Class          |
| ----- | -------------- |
| 100   | Trees          |
| 200   | Lush Bushes    |
| 300   | Dry Grass      |
| 500   | Dry Bushes     |
| 550   | Ground Clutter |
| 600   | Flowers        |
| 700   | Logs           |
| 800   | Rocks          |
| 7100  | Landscape      |
| 10000 | Sky            |

Folder structure:

```
dataset/
 ├── Train/
 │    ├── images/
 │    └── masks/
 ├── Val/
 │    ├── images/
 │    └── masks/
 └── testImages/
```


---

## 🧠 Model

You may use any semantic segmentation architecture (e.g., U-Net, DeepLabV3+, custom CNN).

This repository includes:

* `train.py` – training script
* `test.py` – evaluation on unseen images
* `config.yaml` – model + hyperparameters
* `runs/` – logs and checkpoints

---

## ⚙️ Environment Setup

### 1. Install Anaconda / Miniconda

Ensure Conda is installed.

### 2. Create Environment

Navigate to `ENV_SETUP/` and run:

**Windows**

```bash
setup_env.bat
```

**Mac / Linux**

Create and run `setup_env.sh` with equivalent commands.

This creates an environment named:

```bash
conda activate EDU
```

---

## ▶️ Training

Activate environment:

```bash
conda activate EDU
```

Start training:

```bash
python train.py
```

Outputs:

* Model checkpoints → `runs/`
* Training logs
* Loss curves

---

## 🧪 Testing (Unseen Environment)

Evaluate model robustness:

```bash
python test.py
```

This produces:

* Predicted masks
* IoU score
* Loss metrics

Use this as your **benchmark** for improvement.

---

## 📊 Evaluation Metrics

Primary metric:

* **IoU (Intersection over Union)** – measures pixel-level accuracy

Additional analysis:

* Training / validation loss graphs
* Failure case visualization
* Class-wise performance

---

## 📈 Expected Deliverables

### ✅ Trained Model

* Model weights
* Training & inference scripts
* Configuration files

### ✅ Performance Report

* Final IoU score
* Loss curves
* Failure case analysis
* Optimization steps


Storytelling flow:

**Problem → Fix → Results → Challenges → Future Work**

---

## 🚀 Future Improvements

* Domain adaptation
* Self-supervised learning
* Data augmentation
* Class imbalance handling
* Lightweight models for faster inference

---

## 🙌 Acknowledgements

Duality AI Falcon Platform
GHR 2.0 Hackathon Team
