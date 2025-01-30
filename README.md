# Image Classification Competition - Flora & Fauna

This repository contains my solution for the **Image Classification Competition - Flora & Fauna**. The goal of the competition was to classify images of plants and animals into 10 categories with the highest F1 score.

## 🏆 Competition Details
- **Competition Link:** [Deep Learning Practice - Image Classification](https://www.kaggle.com/competitions/deep-learning-practice-image-classification/overview)
- **Task:** Classify images into one of 10 categories:
  - Amphibia (0)
  - Animalia (1)
  - Arachnida (2)
  - Aves (3)
  - Fungi (4)
  - Insecta (5)
  - Mammalia (6)
  - Mollusca (7)
  - Plantae (8)
  - Reptilia (9)
- **Dataset:**
  - **Train Set:** 10,000 images (10 classes, 1,000 per class)
  - **Test Set:** 2,000 images (to predict labels)
  - [Download the dataset here](https://drive.google.com/drive/folders/1dwGzQwooU4PT642faBxBj_CS6OB_FiFE?usp=sharing)

## 🚀 Model & Approach
- **Pretrained Model:** `eva02_large_patch14_448.mim_m38m_ft_in22k_in1k` (from TIMM)
- **Framework:** PyTorch & Torchvision
- **Data Augmentation:**
  - `AutoAugment (IMAGENET policy)`
  - `RandomHorizontalFlip`
  - `ColorJitter (Brightness, Contrast, Saturation, Hue)`
- **Training Strategy:**
  - Used **AdamW** optimizer with **CosineAnnealingLR** scheduler
  - Early stopping with patience of 5 epochs
  - Weighted **F1 Score** as evaluation metric
  - Used **AMP (Automatic Mixed Precision)** for efficient training
- **Inference:**
  - Model checkpointing to save the best model
  - Batch predictions on the test set

## 📂 Repository Structure
```
|-- README.md               # This file
|-- notebook.ipynb          # Kaggle notebook with full code
|-- submission.csv          # Final submission file
```

## 📌 Dependencies
Make sure you have the required libraries installed:
```bash
pip install torch torchvision timm pandas tqdm
```

## 📊 Results
- **Best Validation F1 Score:** *0.9421*
- **Final Test Submission:** *0.94497*

## 🔥 Future Improvements
- Fine-tune more layers of the model
- Use **MixUp / CutMix** for better generalization
- Implement **Test-Time Augmentation (TTA)**
- Experiment with smaller image sizes for faster training

## 🤝 Contributions & Feedback
If you have suggestions or improvements, feel free to open an issue or a pull request! 🚀

📍 Check out my Kaggle profile [here](https://www.kaggle.com/canisqmisra)

