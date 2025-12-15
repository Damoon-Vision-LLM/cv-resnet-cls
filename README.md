# 🐶 Dog Breed Image Classification using ResNet
ResNet architecture has been used as a clasical baseline for calssification


## 🧠 Model Architecture (Inception-ResNet-v2 + Custom Classification Head)

```text
┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━┓
┃ Layer (type)                    ┃ Output Shape           ┃       Param # ┃
┡━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━┩
│ inception_resnet_v2             │ (None, 9, 9, 1536)     │    54,336,736 │
│ (Functional)                    │                        │               │
├─────────────────────────────────┼────────────────────────┼───────────────┤
│ global_average_pooling2d        │ (None, 1536)           │             0 │
│ (GlobalAveragePooling2D)        │                        │               │
├─────────────────────────────────┼────────────────────────┼───────────────┤
│ batch_normalization_203         │ (None, 1536)           │         6,144 │
│ (BatchNormalization)            │                        │               │
├─────────────────────────────────┼────────────────────────┼───────────────┤
│ dense (Dense)                   │ (None, 512)            │       786,944 │
├─────────────────────────────────┼────────────────────────┼───────────────┤
│ dense_1 (Dense)                 │ (None, 256)            │       131,328 │
├─────────────────────────────────┼────────────────────────┼───────────────┤
│ dropout (Dropout)               │ (None, 256)            │             0 │
├─────────────────────────────────┼────────────────────────┼───────────────┤
│ dense_2 (Dense)                 │ (None, 128)            │        32,896 │
├─────────────────────────────────┼────────────────────────┼───────────────┤
│ dense_3 (Dense)                 │ (None, 120)            │        15,480 │
└─────────────────────────────────┴────────────────────────┴───────────────┘

Total params: 55,309,528 (210.99 MB)  
Trainable params: 969,720 (3.70 MB)  
Non-trainable params: 54,339,808 (207.29 MB)
```

---
## 🚀 Features  
- Preprocessing and loading of the 120-class dog breed dataset  
- Configurable training pipeline (epochs, learning rate, augmentation, freezing layers)  
- Custom classification head on top of ResNet  

---

## 📁 Project Structure
```
├── Image_Classification.ipynb     # Main training notebook
├── requirements.txt               # Python dependencies
└── data/                          # (Create manually) dataset folder
    └── <dataset files here>
```

---

## 🔧 Installation

### 1️⃣ Install dependencies

```bash
pip install -r requirements.txt
```

---

## 📥 Download the Dataset  
Download the **120 Dog Breed Dataset** from Kaggle and place it into the `data/` folder:

🔗 https://www.kaggle.com/datasets/vikaschauhan734/120-dog-breed-image-classification

---

## ▶️ How to Run the Notebook

1. Open **Image_Classification.ipynb**  
2. Follow the guided steps to:  
   - Load and prepare the dataset  
   - Apply image augmentation  
   - Build and modify the ConvNeXt model  
   - Adjust training parameters (lr, freeze layers, dropout, etc.)  
3. Train the model 

---


## 📊 Results  
Model trained with frozen backbone and tuned classification head achieved:  
- ✔️ Stable convergence  
- ✔️ Strong performance across 120 breeds  
- ✔️ Ability to generalize with moderate augmentation

90% accuracy achived in the the best taining 

<img src="sample results/loss.png" size="400">
---
